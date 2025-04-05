// EJERCICIO01 - CODIGO 
mixin Autenticacion {
  void iniciarSesion(String email, String contrasena) {
    print("Iniciando sesión con:");
    print("Email: $email");
    print("Contraseña: $contrasena");
  }
}

class Usuario {
  String nombre;
  String email;
  String contrasena;

  Usuario(this.nombre, this.email, this.contrasena) {
    print("Constructor de Usuario");
  }

  void mostrarDatos() {
    print("Nombre: $nombre");
    print("Email: $email");
  }
}


class UsuarioAutenticado extends Usuario with Autenticacion {
  UsuarioAutenticado(String nombre, String email, String contrasena)
      : super(nombre, email, contrasena) {
    print("Constructor de UsuarioAutenticado");
  }

  @override
  void mostrarDatos() {
    super.mostrarDatos();
    print("Contraseña: $contrasena");
  }
}

void main() {
  var usuario = UsuarioAutenticado("Patrick", "patrick@email.com", "1234");
  usuario.mostrarDatos();
  usuario.iniciarSesion(usuario.email, usuario.contrasena);
}
