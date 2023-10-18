package Socket;
import java.io.*;
import java.net.Socket;
import java.net.ServerSocket;
public class ServerTCP {
    public static void main(String argv[]) throws Exception
    {
        String sentence_from_client;
        String sentence_to_client;
        ServerSocket welcomeSocket = new ServerSocket(8808);

        while(true) {

            Socket connectionSocket = welcomeSocket.accept();

            //Tạo input stream, nối tới Socket
            BufferedReader inFromClient =
                    new BufferedReader(new
                            InputStreamReader(connectionSocket.getInputStream()));

            //Tạo outputStream, nối tới socket
            DataOutputStream outToClient =
                    new DataOutputStream(connectionSocket.getOutputStream());
            // Xử lý phần client truyền lên ở đây ...
            sentence_from_client = inFromClient.readLine().toUpperCase();
            sentence_to_client = sentence_from_client + "\n";
            outToClient.writeBytes(sentence_to_client);

            if ( sentence_from_client.equals("X") ) return;
        }

    }
}
