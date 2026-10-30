# Bankszámla és Mockito tesztek
A BankAccount egy bankszámlát kezel.
A BankService befizetés után értesítést küld.
Az ExchangeRateService árfolyamot ad vissza.

Java 17 vagy újabb JDK és Maven szükséges.
A projekt mappájában:
mvn clean test

## Tesztek

- BankAccountTest: 18 eset a befizetésre, pénzfelvételre és hibás műveletekre
- BankServiceTest: mock() használata
- BankServiceAnnotationTest: @Mock és @InjectMocks használata
- ExchangeRateServiceTest: a beállított árfolyamválasz és három átváltás ellenőrzése
Összesen 30 teszteset van

## Verziók
- Java 17
- JUnit Jupiter 5.11.3
- Mockito 5.14.2
- Maven 3.9.9
