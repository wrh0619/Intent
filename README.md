实验五intent：<br>
实验截图：<br>
![image](https://github.com/wrh0619/Intent/blob/master/images/1.JPG)<br>
![image](https://github.com/wrh0619/Intent/blob/master/images/2.JPG)<br>
关键代码：<br>
MainActivity.java
```
package com.example.intenttest;
import android.content.Intent;
import android.net.Uri;
import android.provider.ContactsContract;
import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.SearchView;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(final Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        final Button send = findViewById(R.id.submit);
        send.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                EditText editText = findViewById(R.id.web);
                String website = editText.getText().toString();
                Intent sendIntent=new Intent();
                sendIntent.setAction(Intent.ACTION_VIEW);
                sendIntent.setData(Uri.parse(website));
                startActivity(sendIntent);
            }
        })
    }
}
```


activity_main.xml
```
<?xml version="1.0" encoding="utf-8"?>
<android.support.constraint.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity"
    android:background="@drawable/back">

    <EditText
        android:id="@+id/web"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginTop="95dp"
        android:layout_marginBottom="101dp"
        android:hint="type your website"
        app:layout_constraintBottom_toTopOf="@+id/submit"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:id="@+id/submit"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginStart="160dp"
        android:layout_marginTop="188dp"
        android:gravity="center"
        android:text="转到"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

</android.support.constraint.ConstraintLayout>
```
