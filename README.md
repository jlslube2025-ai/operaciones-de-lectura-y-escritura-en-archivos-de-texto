# operaciones-de-lectura-y-escritura-en-archivos-de-texto
Tarea sobre operaciones de lectura y escritura en archivos de texto, aplicando lo aprendido en clase sobre el manejo de archivos con Java
import java.io.*;  // Importa las clases necesarias para manejo de archivos

public class TrabajoConArchivos {

    public static void main(String[] args) {

        // Nombre del archivo donde se guardarán las notas
        String nombreArchivo = "mis_notas.txt";

        // ---------------------------
        // ESCRITURA DEL ARCHIVO
        // ---------------------------
        try {
            // FileWriter permite escribir caracteres en un archivo
            // PrintWriter facilita escribir texto de forma formateada
            FileWriter fw = new FileWriter(nombreArchivo);
            PrintWriter pw = new PrintWriter(fw);

            // Escribimos tres líneas de notas personales
            pw.println("Hoy aprendí a manejar archivos de texto en Java.");
            pw.println("Comprendí la importancia de cerrar los flujos después de usarlos.");
            pw.println("Practicar con ejemplos reales ayuda a reforzar el aprendizaje.");

            // Cerramos los flujos para liberar recursos
            pw.close();
            fw.close();

            System.out.println("Archivo creado y escrito correctamente.\n");

        } catch (IOException e) {
            System.out.println("Error al escribir en el archivo: " + e.getMessage());
        }

        // ---------------------------
        // LECTURA DEL ARCHIVO
        // ---------------------------
        try {
            // FileReader y BufferedReader permiten leer texto línea por línea
            FileReader fr = new FileReader(nombreArchivo);
            BufferedReader br = new BufferedReader(fr);

            String linea;
            System.out.println("Contenido del archivo:");

            // Leemos el archivo línea por línea
            while ((linea = br.readLine()) != null) {
                System.out.println("Nota: " + linea);
            }

            // Cerramos los flujos
            br.close();
            fr.close();

        } catch (IOException e) {
            System.out.println("Error al leer el archivo: " + e.getMessage());
        }
    }
}
