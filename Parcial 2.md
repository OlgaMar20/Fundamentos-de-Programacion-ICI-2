'''dart 
## Clase del 26 de Septiembre
import 'dart:io';
//calculadora que lea dos numeros del teclado y obtenga suma, resta, multiplicación y
//division, usando funciones y asingnado valores a dos variables

void main() {
  String op = leerDatos("Indica la operación [+,-,*,/]");
  int num1 = int.parse(leerDatos("Dame el primer número"));
  int num2 = int.parse(leerDatos("Dame el segundo número"));
  print("${calculadora(op, num1, num2)}");
}

String leerDatos(String mensaje) {
  print(mensaje);
  String data = (stdin.readLineSync()!);
  return data;
}

String calculadora(String op, int n1, int n2) {
  if (op == "+") {
    return "$n1 + $n2 = ${suma(n1, n2)}";
  } else if (op == "-") {
    return "$n1 - $n2 = ${resta(n1, n2)}";
  } else if (op == "*") {
    return "$n1 * $n2 = ${multi(n1, n2)}";
  } else if (op == "/") {
    return "$n1 / $n2 = ${divi(n1, n2)}";
  } else {
    return "Operación inválida";
  }
}

int suma(int num1, int num2) => num1 + num2;
int resta(int num1, int num2) => num1 - num2;
int multi(int num1, int num2) => num1 * num2;
int divi(int num1, int num2) => num1 ~/ num2;

## Clase del 27 de septiembre
void main() {
  //tipado explicito
  int miEntero=10;
  double miDouble=3.1416;
  print(miEntero is int);
  print(miDouble is double);
  print("Hola mundo");
  // tipo de variables
  num miNumber1=10;
  num miNumber2=3.1416;
  print(miNumber1 is num);
  print(miNumber2 is num);
  
  String miCadena="Hola";
  print(miCadena is String);
  
  dynamic miDinamico="Hola";
  print(miDinamico);
  miDinamico=3.1416;
  print(miDinamico);
  
  bool miBool=true;
  print(!miBool);
  
  //constantes= declaracion de constantes con tipo explicito
  //tiempo de compilacion
  const double miPI=3.1416;
  print(miPI);
  //tiempo de ejecucion
  final double miPI2;
  miPI2=3.1416;
  print(miPI2);
   //runtimrtype indica que tipo de dato es 
  num minumero;
  minumero=3.1416;
  print(minumero.runtimeType);
  //declaracion con var (Inferencia de tipo)
  var numero=100;
  print(numero.runtimeType);
  var numero2=9.81;
  var nombre="Alex";
  print(nombre.runtimeType);
  
  var resultado;
  resultado = numero + numero2;
  print(resultado.runtimeType);
  
  const numero1=19.5;
  const numero22=10;
  final total = (numero1*numero22).toInt();
  print(total);
  
  //int nHexa1=0*F;
  //int nHexa2=0*F;
  //print(nHexa1*nHexa2);
  
  var nOctal=125.toRadixString(8);
  print(nOctal.runtimeType);
  
  var nH=125.toRadixString(16);
  print(nH.runtimeType);
  //concatenar cadenas
  String nombreCurso="Programacion Funcional";
  String carrera="ICI";
  print(carrera +"" + nombreCurso);
  //Interpolacion de cadenas
  print("$carrera $nombreCurso");
  //Usar cuando llama una funcion
  print("${getCarrera} ${nombreCurso}");
  var num1=4;
  print("El cuadrado de $num1 es ${cuadrado (num1)}");
  
  print("En un lugar de\n"
       "la mancha de cuyo\n"
       "nombre no quiero acordarme");
  //Hacer en flutter para que corra
  //print("Dame un nombre: ");
  //final nombreu= stdin.readlineSync();
  //print("Tu nombre es $nombreu");
  
  //Listas
  final calificaciones=[10,6,9,8,10,8];
  print(calificaciones);
  calificaciones.add(2);
  print(calificaciones);
  for (var i=0;i<calificaciones.length;i++){
    print(calificaciones[i]);
  }
  //condicionales 
  int n1=5,n2=3;
  if(n1>n2){
    print("$n1>$n2");
  } else if (n1==n2){
    print("$n1=$n2");
  } else{
    print("$n1>$n2");
  }
 
  //operador ternario
  int n11=9,n22=4;
  int mayor;
  if(n1>n2){
    mayor=n1;
  } else {
    mayor=n2;
  }
  print("El mayor es: $mayor");
  
  int menor;
  n11<n22? menor=n1:menor=n2;
  print("El menor es: $menor");
  
  menor=n1<n2?n1:n2;
  print("El MENOR es: $menor");
  
  //sentencia switch case
  var dia;
  dia= "martes";
  switch(dia){
    case 1:
      print("El dia es ${getDay(dia)}");
      break;
    case "martes":
      print("Hoy es martes");
      break;
    default:
      print("Dia no conocido");
      
  }
  //ciclos 
  for (var i=0;i<=5;i++){
    print("$i");
  }
  var numeros=[1,2,3,4,5];
  for (var e in numeros){
    print ("$e");  
  }
  var numeros1=["1","2",3.1416,true,5];
  for (var e in numeros1){
    print ("$e");  
  }
  //numeros.forEach(e){
    //print("$e");
  //}
  //var nume=List<int>.generate(10,(i)=i+1)
  //print(nume);
  //var sum=0;
  //nume.forEach((e)==sum+=e );
  //print(sum);
  //var nume1=1;
  //while (nume1<=5){
    //stdout.write("$nume1\n");
    //nume1++;
    //}
  //print("");
  //var numee1=1;
 
  //do{
    //stdout.write("$numee1\n");
    //nume1++;
    //} while (numee1<=5);
}
String getCarrera(){
  return "ICI";
}
int cuadrado(int num1){
  return num1*num1;
}
String getDay(int numd)
{
  if (numd==1){
    return "lunes";
  }else{
    return "";
  }
}

import 'dart:math';

##Clases del 03 y 04 de octubre
void main() {
  num a = 3;
  a as int; // casting sobre datos numericos
  print(a.isEven); // determina si es par o impar

  var infInt = 5;
  var infDouble = 9.81;
  print("${infInt.runtimeType}"); //menciona que tipo de variable es
  print("${infDouble.runtimeType}");

  num infNum; //si no especificamos valor marca error
  infNum = 3.6;
  print("${infNum.runtimeType}");
  infNum = 5;
  print("${infNum.runtimeType}");

  print(5.isOdd); //saber si es impar true

  int a1 = -3000;
  double b = 9.5;

  print(a1.isNegative); //saber si es negativo
  print(b.floor()); //piso numero hacia arriba
  print(b.ceil()); //cielo numero hacia arriba
  print(b.round()); //redondea
  print(b.truncate());

  var c = "Hola";
  print(!b.isNaN); //saber si es un numero is a number

  //operaciones aritmeticas
  print((10 / 3).truncate());
  //print(10 / 3);//PONER S INVERTIDA antes de la diagonal
  print(cos(45 * pi / 180));
  print(sin(45 * pi / 180));
  print(sqrt(9));
  print(pow(2, 3));
  print(max(6, 10));
  print(min(6, 10));

  //incrementos y decrementos
  var contador1 = 0;
  contador1 = contador1 + 1;
  print(contador1);
  contador1 += 1;
  print(contador1);
  contador1++;
  print(contador1);
  ++contador1;
  print(contador1);

  var w = 10;
  print(++w); //imprime 11 incremeta
  w = 10;
  print(w++); //imprime 10 e incrementa
  print(w); //imprime ya incrementado

  var contador = 10;
  contador = contador - 1;
  print(contador);
  contador -= 1;
  print(contador);
  contador--;
  print(contador);
  --contador;
  print(contador);

  var w1 = 10;
  print(--w1);
  w1 = 10;
  print(w1--);
  print(w1);

  // castign con tipos de datos
  int a2 = 5;
  double b2 = 3.5;

  print(a2.toDouble());
  print(b2.toInt());
  print("El valor es: $a2");
  print("El valor es: " + a2.toString());
  print(a2 + b2);
  print(a2 / b2);

  //convertir string a numerico
  var a3 = "10";
  var b3 = "8.5";

  print(int.parse(a3) * 2);
  print(double.parse(b3) * 2);

  var numero = 3.14161592;
  print(numero.toStringAsFixed(3)); //INDICAR CUANTOS DECIMALES
}
##Clases del 10 y 11 de Octubre 
//encapsulación
void main() {
  //User usuario = User(nombre:"Alex", edad: 15); //constructores
  User usuario = User.nombre("Paco");
  User usuario2 = User.edad(15);
  print(usuario.getNombre); //metodo
  //print(usuario.nombre); //propiedad
  //print(usuario2.edad);
  print(usuario2.getEdad);
  //usuario.reporteUser();
  //usuario2.reporteUser();
  //print(usuario);
  //usuario.nombre = "Alex";
  //usuario.edad = 18;
  //usuario.reporteUser();
  //User usuario2 = User(nombre: "Maria", edad: 25);
  //usuario2.nombre = "Maria";
  //usuario2.edad = 25;
  //print(usuario.getNombre);
  //print(usuario.getEdad);
  //usuario2.reporteUser();
}

/// Clase que representa un usuario
class User {
  ///Propiedad nombre tipo string
  String? _nombre;
  //String? nombre;

  ///Propiedad edad tipo int mayor de 0(cero)
  int? _edad;
  //int? edad;

  ///Método que imprime un usuario
  void reporteUser() {
    print(_nombre);
    print(_edad);
    //print(nombre);
    //print(edad);
  }

  //Constructor
  //Short hand=optimizado version corta del constructor
  //User(this._nombre, this._edad);
  //User(String nombre, int edad) {
  //constructor basico
  //print("Este es el constructor de User");
  //this._nombre = nombre;
  //this._edad = edad;
  //}
  //Argumentos o propiedades nombradas(entre llaves,puede ir en cualquier
  //lugar no posicional)=
  //aqui no deja poner la clase privada
  //entonces tenemos que quitar los _ a nombre y edad y cambiar el
  //nombre a set y get por setEdad y setNombre
  //User({this.nombre, this.edad});
  //User.nombre(this.nombre);
  User.nombre(String nombre) {
    //para eliminar el null
    this._nombre = nombre;
    this._edad = 0;
  }
  //User.edad(this.edad);
  User.edad(int edad) {
    this._edad = edad;
    this._nombre = "-";
  }

  void set setNombre(String nombre) => nombre = nombre;
  //void set nombre(String nombre) {
  //_nombre = nombre;
  //}

  void set setEdad(int edad) => edad = edad; //fat arround= flecha gorda

  String get getNombre => _nombre!;
  //String get getNombre {
  //return nombre!;
  //}

  int get getEdad => _edad!;
}

##Clase del 17 de Octubre 
//Actividad realizada en clase
void main() {
  Vehiculo mikia = Vehiculo("rio", 4, "kia", "Gris");
  Vehiculo mikia2 = Vehiculo.modelo("RIO");
  // mikia.setllantas = 4;
  // mikia.setModelo = "rio";
  // mikia.setMarca = "kia";
  //mikia.setColor = "Gris";
  print(mikia.getLlantas);
  print(mikia.getMarca);
  print(mikia.getModelo);
  print(mikia.getColor);
  mikia.estacionar();
  mikia.frenar();
  mikia.encender();
}

/// Clase que representa un usuario
class Vehiculo {
  int? _llantas;
  String? _marca;
  String? _modelo;
  String? _color;
  void estacionar() {
    print("Estacionado");
  }

  void frenar() {
    print("Frenar");
  }

  void encender() {
    print("Enceder");
  }

  Vehiculo(String marca, int llantas, String modelo, String color) {
    //print("Este es el constructor de User");
    this._llantas = llantas;
    this._marca = marca;
    this._modelo = modelo;
    this._color = color;
  }
  Vehiculo.modelo(String modelo) {
    this._modelo = modelo;
  }

  void set setllantas(int llantas) => _llantas = llantas;

  void set setMarca(String marca) => _marca = marca;

  void set setModelo(String modelo) => _modelo = modelo;

  void set setColor(String color) => _color = color;

  int get getLlantas => _llantas!;

  String get getMarca => _marca!;

  String get getModelo => _modelo!;

  String get getColor => _color!;
}
'''
