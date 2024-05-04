Zadanie 1. Proszę zrealizować aplikację obiektową, która powinna odznaczać się następującymi cechami:
 Aplikacja powinna zawierać klasę „Samochod”, umożliwiającą przechowywanie określonych informacji oraz wykonywanie określonych działań.
 Klasa „Samochod” ma umożliwiać przechowywanie informacji na temat samochodu: marki, modelu, ilości drzwi, pojemności silnika, średniego spalania na 100 km.
 Klasa „Samochod” ma posiadać właściwości dostępowe do wszystkich pól, które nie są statyczne.  Klasa „Samochod” ma umożliwiać przechowywanie informacji na temat liczby utworzonych obiektów tej klasy (poprzez pole statyczne).
Strona HTML
Obrazy
10
 Klasa „Samochod” ma zawierać konstruktor domyślny oraz konstruktor przyjmujący parametry.  Klasa „Samochod” ma umożliwiać obliczanie średniego spalania na danej trasie na podstawie podanej długości tej trasy.
 Klasa „Samochod” ma umożliwiać obliczanie ceny paliwa potrzebnego do przejechania danej trasy na podstawie podanej długości trasy i ceny paliwa za litr.  Klasa „Samochod” ma umożliwiać wypisanie na ekran konsoli wszystkich informacji o danym samochodzie (wartości pól, które nie są statyczne).
 Klasa „Samochod” ma umożliwiać wypisanie na ekran konsoli informacji o liczbie utworzonych obiektów (poprzez metodę statyczną).
 Uwagi:
 Do wypisywania treści na ekranie konsoli służy polecenie: Console.WriteLine([treść])
 Po wykonaniu zadania należy je przetestować za pomocą kodu testowego umieszczonego na końcu opisu realizacji zadania.
 Reprezentacja klasy na diagramie UML:
Aby zrealizować zadanie należy wykonać następujące kroki:
 Proszę o utworzenie nowego projektu konsolowego w środowisku Visual Studio.  Proszę o utworzenie klasy „Samochod”.  Proszę o utworzenie prywatnych pól klasy „Samochod” o nazwie: „marka”, „model”, „iloscDrzwi”, „pojemnoscSilnika”, „srednieSpalanie”. Proszę zwrócić uwagę na odpowiedni dobór typów pól. Np.:
private double srednieSpalanie;
 Proszę o utworzenie właściwości dostępowych do wszystkich pól (oprócz pola statycznego). Np.: public double SrednieSpalanie { get { return srednieSpalanie; }
11
set { srednieSpalanie = value; } }
 Proszę o utworzenie w klasie „Samochod” prywatnego statycznego pola typu int o nazwie „iloscSamochodow” i przypisanie mu wartości 0:
private static int iloscSamochodow = 0;
 Proszę o utworzenie konstruktora domyślnego, który wszystkim polom przyporządkowuje wartości: „nieznana” lub „nieznany” dla pól typu string, „0” dla pól typu int, „0.0” dla pól typu double. Wywołanie konstruktora powinno zwiększać o 1 wartość pola statycznego „iloscSamochodow”. Proszę pamiętać o tym, że konstruktor domyślny nie przyjmuje żadnych parametrów.  Proszę o utworzenie konstruktora, przyjmującego następujące parametry: „marka_”, „model_”, „iloscDrzwi_”, „pojemnoscSilnika_”, „srednieSpalanie_”. Typy parametrów powinny odpowiadać typom pól klasy „Samochod”. Konstruktor ma przekazywać wartości parametrów polom. Wywołanie konstruktora powinno zwiększać o 1 wartość pola statycznego „iloscSamochodow”.
 Proszę o utworzenie prywatnej metody „ObliczSpalanie” zwracającej wartość typu double i przyjmującej parametr „dlugoscTrasy” typu double. Metoda ta ma obliczać spalanie samochodu na podstawie podanej wartości długości trasy i wartości pola „srednieSpalanie”. Spalanie obliczamy według wzoru:
spalanie = (srednieSpalanie * dlugoscTrasy) / 100.0;
 Proszę o utworzenie publicznej metody „ObliczKosztPrzejazdu” zwracającej wartość typu double i przyjmującej parametry „dlugoscTrasy” typu double i „cenaPaliwa” typu double. Metoda ta ma obliczać koszt przejazdu na trasie o podanej długości, zakładając podaną cenę paliwa za litr. Metoda ta ma wykorzystywać prywatną metodę „ObliczSpalanie”. Koszt przejazdu obliczamy według wzoru:
kosztPrzejazdu = spalanie * cenaPaliwa;
 Proszę o utworzenie publicznej metody „WypiszInfo” zwracającej wartość typu void i nie przyjmującej żadnych parametrów. Metoda ta ma wypisywać na ekranie konsoli wartości wszystkich pól klasy „Samochod”. Np.:
Console.WriteLine("Marka: " + marka);
 Proszę o utworzenie publicznej statycznej metody „WypiszIloscSamochodow” zwracającej wartość typu void i nie przyjmującej żadnych parametrów. Metoda ta ma wypisywać na ekranie konsoli wartość pola statycznego „iloscSamochodow”.
 Proszę o przetestowanie poprawności wykonania zadania za pomocą kodu testowego:
12
Samochod s1 = new Samochod(); s1.WypiszInfo(); s1.Marka = "Fiat"; s1.Model = "126p"; s1.IloscDrzwi = 2; s1.PojemnoscSilnika = 650; s1.SrednieSpalanie = 6.0; s1.WypiszInfo(); Samochod s2 = new Samochod("Syrena", "105", 2, 800, 7.6); s2.WypiszInfo(); double kosztPrzejazdu = s2.ObliczKosztPrzejazdu(30.5, 4.85); Console.WriteLine("Koszt przejazdu: " + kosztPrzejazdu);
Samochod.WypiszIloscSamochodow(); Console.ReadKey();
