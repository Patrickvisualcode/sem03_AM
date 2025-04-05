 // EJERCICIO05 - CODIGO

mixin ValidacionVoto {
  void validarVoto(int edad) {
    if (edad >= 18) {
      print("El votante es elegible para votar.");
    } else {
      print("El votante NO es elegible para votar.");
    }
  }
}

class Votante {
  String nombre;
  int edad;
  bool haVotado;

  Votante(this.nombre, this.edad, this.haVotado) {
    print('Constructor de Votante');
  }

  void mostrarDatos() {
    print('Nombre: $nombre');
    print('Edad: $edad');
    print('¿Ha votado?: ${haVotado ? "Sí" : "No"}');
  }
}

class VotanteValido extends Votante with ValidacionVoto {
  VotanteValido(String nombre, int edad, bool haVotado)
      : super(nombre, edad, haVotado) {
    print('Constructor de VotanteValido');
  }
}


void main() {
  VotanteValido v = VotanteValido("Patrick", 20, false);
  v.mostrarDatos();
  v.validarVoto(v.edad);
}
