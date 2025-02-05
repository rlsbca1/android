MULTITHREADING

```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <Button
        android:id="@+id/button"
        android:layout_width="112dp"
        android:layout_height="97dp"
        android:onClick="india"
        android:text="Button"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.239"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.609" />

    <Button
        android:id="@+id/button2"
        android:layout_width="113dp"
        android:layout_height="91dp"
        android:onClick="karnataka"
        android:text="Button"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.81"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.609" />

    <ImageView
        android:id="@+id/imageView"
        android:layout_width="250dp"
        android:layout_height="247dp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.53"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.169"
        tools:srcCompat="@tools:sample/avatars" />
</androidx.constraintlayout.widget.ConstraintLayout>
```
```

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.ImageView;

public class MainActivity extends AppCompatActivity 
{
    Button button,button2;
    ImageView imageView;

    @Override
    protected void onCreate(Bundle savedInstanceState) 
   {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        button=(Button)findViewById(R.id.button);
        button2=(Button)findViewById(R.id.button2);
        imageView=(ImageView)findViewById(R.id.imageView);
    }

            public void india(View view)
            {
               new Thread(new Runnable() 
              {
                   @Override
                   public void run()
                   {
                      imageView.post(new Runnable() {
                          @Override
                          public void run()
                          {
                              imageView.setImageResource(R.drawable.india);
                          }
                      });
                   }
               }).start();
            }

            public void karnataka(View V)
            {
                new Thread (new Runnable() {
                    @Override
                    public void run() {
                        imageView.post(new Runnable() {
                            @Override
                            public void run() {
                                imageView.setImageResource(R.drawable.karnataka);

                            }
                        });
                    }
                }).start();
            }
}
```
