## Getting Started

Welcome to the VS Code Java world. Here is a guideline to help you get started to write Java code in Visual Studio Code.

## Folder Structure

The workspace contains two folders by default, where:

- `src`: the folder to maintain sources
- `lib`: the folder to maintain dependencies

Meanwhile, the compiled output files will be generated in the `bin` folder by default.

> If you want to customize the folder structure, open `.vscode/settings.json` and update the related settings there.

## Dependency Management

The `JAVA PROJECTS` view allows you to manage your dependencies. More details can be found [here](https://github.com/microsoft/vscode-java-dependency#manage-dependencies).


modificador tipoDeRetorno nombreDelMetodo(parámetros) {
    // cuerpo del método
    // instrucciones que realiza el método
    return valor; // si no es void

    modificador	Define la visibilidad del método. Ejemplo: public, private, protected.
tipoDeRetorno	El tipo de dato que devuelve el método. Si no devuelve nada, se usa void.
nombreDelMetodo	El nombre del método. Debe seguir las reglas de nombres en Java (camelCase).
parámetros	Lista de valores de entrada (tipo y nombre). Puede estar vacía.
return	Se usa si el método devuelve un valor (excepto si es void).


import java.util.ArrayList;

public class AnalizadorNotas {

    // Método que analiza una lista de calificaciones y devuelve observaciones
    public ArrayList<String> analizarNotas(ArrayList<Double> calificaciones) {
        ArrayList<String> observaciones = new ArrayList<>();

        if (calificaciones == null || calificaciones.isEmpty()) {
            observaciones.add("La lista de calificaciones está vacía.");
            return observaciones;
        }

        for (int i = 0; i < calificaciones.size(); i++) {
            double nota = calificaciones.get(i);
            String mensaje;

            if (nota >= 4.5) {
                mensaje = "Nota " + nota + ": Excelente";
            } else if (nota >= 3.0) {
                mensaje = "Nota " + nota + ": Aceptable";
            } else {
                mensaje = "Nota " + nota + ": Insuficiente";
            }

            observaciones.add(mensaje);
        }

        return observaciones;
    }

    // Método main para probarlo
    public static void main(String[] args) {
        AnalizadorNotas analizador = new AnalizadorNotas();
        ArrayList<Double> notas = new ArrayList<>();
        notas.add(4.7);
        notas.add(3.2);
        notas.add(2.5);
        notas.add(5.0);

        ArrayList<String> resultados = analizador.analizarNotas(notas);

        // Imprimir resultados
        for (String r : resultados) {
            System.out.println(r);
        }
    }
}