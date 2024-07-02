import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.layout.GridPane;
import javafx.scene.image.Image;
import javafx.scene.image.ImageView;
import javafx.stage.Stage;

public class Exercise_14_01 extends Application {
    @Override
    public void start(Stage primaryStage) {
        // pane to hold the image views
        GridPane pane = new GridPane();

        // Place nodes in the pane
        pane.add(new ImageView(new Image("image/US.gif")), 0, 0);
        pane.add(new ImageView(new Image("image/UK.gif")), 1, 0);
        pane.add(new ImageView(new Image("image/france.gif")), 0, 1);
        pane.add(new ImageView(new Image("image/china.gif")), 1, 1);

        // Create a scene and place it in the stage
        Scene scene = new Scene(pane);
        primaryStage.setTitle("Exercise_14_01"); // Set the stage title
        primaryStage.setScene(scene); // Place the scene in the stage
        primaryStage.show(); // Display the stage
    }

    public static void main(String[] args) {
        launch(args);
    }
}
