# Simple-Chat-Application
A simple console-based chat application that allows multiple users to send messages to each other.



    import java.util.Scanner;

      public class ChatApplication {
        public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        ChatRoom chatRoom = new ChatRoom();

        System.out.println("Welcome to the Chat Application!");
        System.out.print("Enter your username: ");
        String username = scanner.nextLine();
        User user = new User(username);
        chatRoom.addUser (user);

        String command;
        do {
            System.out.print("Enter a message (or type 'exit' to quit): ");
            command = scanner.nextLine();

            if (!command.equalsIgnoreCase("exit")) {
                chatRoom.sendMessage(username, command);
                chatRoom.displayAllMessages();
            }
        } while (!command.equalsIgnoreCase("exit"));

        System.out.println("Goodbye, " + username + "!");
        scanner.close();
    }
}

