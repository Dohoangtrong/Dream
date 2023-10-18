package Socket;
import java.io.*;
import java.net.Socket;
public class ClientTCP {
    public static void main(String argv[]) throws Exception
    {
        String sentence_to_server;
        String sentence_from_server;

        BufferedReader inFromUser =
                new BufferedReader(new InputStreamReader(System.in));
        while(true){
            System.out.print("Input from client: ");
            sentence_to_server = inFromUser.readLine();

            //Tạo socket cho client kết nối đến server qua ID address và port
            Socket clientSocket = new Socket("127.0.0.1", 8808);

            //Tạo OutputStream nối với Socket
            DataOutputStream outToServer =
                    new DataOutputStream(clientSocket.getOutputStream());

            //Tạo inputStream nối với Socket
            BufferedReader inFromServer =
                    new BufferedReader(new
                            InputStreamReader(clientSocket.getInputStream()));

            outToServer.writeBytes(sentence_to_server + '\n');

            sentence_from_server = inFromServer.readLine();

            System.out.println("FROM SERVER: " + sentence_from_server);

            // Nếu input là x thì sẽ ngắt kết nối webSocket ở cả Client và Server
            if ( sentence_to_server.equals("x") ){
                clientSocket.close();
                break;
            }
        }
    }
}
