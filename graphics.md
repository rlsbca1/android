
# GRAPHICS

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
        android:layout_width="129dp"
        android:layout_height="65dp"
        android:text="CLICK"
        android:onClick="shreyas"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.498"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.404" />
</androidx.constraintlayout.widget.ConstraintLayout>
```
# MainActivity.java

```

import androidx.appcompat.app.AlertDialog;
import androidx.appcompat.app.AppCompatActivity;

import android.annotation.SuppressLint;
import android.content.DialogInterface;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity
{
    Button b;

    @SuppressLint("MissingInflatedId")
    @Override
    protected void onCreate(Bundle savedInstanceState)
    {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        b=(Button)findViewById(R.id.button);
    }

    public void shreyas(View view)
    {
        AlertDialog.Builder ad = new AlertDialog.Builder(this);
        ad.setTitle("Are you sure you want to continue");

        ad.setPositiveButton("Yes", new DialogInterface.OnClickListener()
        {
            @Override
            public void onClick(DialogInterface dialogInterface, int i)
            {
                Toast.makeText(getApplicationContext(),"Hi Welcome",Toast.LENGTH_LONG).show();
            }
        });

        ad.setNegativeButton("No", new DialogInterface.OnClickListener() 
        {
            @Override
            public void onClick(DialogInterface dialogInterface, int i) 
            {
                finish();
            }
        });

        AlertDialog alertDialog = ad.create();
        alertDialog.show();
    }
}
```
