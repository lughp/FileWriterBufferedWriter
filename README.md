# FileWriter e BufferedWriter

### FileWriter (stream de escrita de caracteres em de arquivos)
* https://docs.oracle.com/javase/10/docs/api/java/io/FileWriter.html

Cria/recria o arquivo: new FileWriter(path)
Acrescenta ao arquivo existente: new FileWriter(path, true)


### BufferedWriter (mais rápido)
* https://docs.oracle.com/javase/10/docs/api/java/io/BufferedWriter.html

### IOException (Exception)
* https://docs.oracle.com/javase/10/docs/api/java/io/IOException.html

### Bloco try-with-resources (Java 7 em diante)
* https://docs.oracle.com/javase/tutorial/essential/exceptions/tryResourceClose.html


```java
import java.io.BufferedWriter;
import java.io.FileWriter;
import java.io.IOException;

public class Program {

    public static void main(String[] args) {

        String[] lines = new String[] {"Good morning", "Good afternoon", "Good night"};

        String path = "c:\\temp\\out.txt";

        try (BufferedWriter bw = new BufferedWriter(new FileWriter(path, true))) { // parâmetro true não recria o arquivo
            for (String line : lines) {
                bw.write(line);
                bw.newLine();
            }
        }
        catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```