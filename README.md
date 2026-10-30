# Bankszámla és Mockito tesztek

A BankAccount egy bankszámlát kezel. Az induló egyenleg 0, befizetni és pénzt felvenni lehet róla. Hibás összeg vagy fedezethiány esetén IllegalArgumentException kivételt dob, és az egyenleg nem változik.

A BankService befizetés után értesítést küld. A NotificationService interfészt konstruktorban kapja meg. A tesztekben ezt mock helyettesíti, így nincs valódi üzenetküldés.

Az ExchangeRateService árfolyamot ad vissza. A tesztekben a when(...).thenReturn(...) állítja be a választ. A CurrencyConverter ezzel az árfolyammal váltja át az összeget.

## Futtatás

Java 17 vagy újabb JDK és Maven szükséges. A java, javac és mvn parancs legyen elérhető. Az első futtatáskor internetkapcsolat kell a függőségek letöltéséhez.

A projekt mappájában:

```text
mvn clean test
```

A teszteredmények a target/surefire-reports mappába kerülnek.

## Tesztek

- BankAccountTest: 18 eset a befizetésre, pénzfelvételre és hibás műveletekre.
- BankServiceTest: mock() használata, a befizetés és az értesítés ellenőrzése verify() segítségével.
- BankServiceAnnotationTest: @Mock és @InjectMocks használata, több befizetés és az értesítés elmaradása hibás összegeknél. Összesen 7 eset.
- ExchangeRateServiceTest: a beállított árfolyamválasz és három átváltás ellenőrzése. Összesen 4 eset.

Összesen 30 teszteset van. A részletes példák a tesztesetek.txt fájlban találhatók.

## Verziók

- Java 17
- JUnit Jupiter 5.11.3
- Mockito 5.14.2
- Maven 3.9.9
