# StringManipulator-in-Android
/*XML code--activity_main.xml*/
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical">

    <EditText
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/edittext1"
        android:hint="Enter the string"/>

    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:id="@+id/show"
        android:text="Show"/>

    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:id="@+id/count"
        android:text="Count"/>

    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:id="@+id/reverse"
        android:text="Reverse"/>

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text=""
        android:id="@+id/text1"/>

</LinearLayout>
/*MainActivity.java*/
package com.example.nimmalavishnu.stringmanipulator;

import android.app.Activity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;
import android.widget.Toast;

public class MainActivity extends Activity {
    Button s, c, r;
    TextView show;
    EditText str1;
        @Override
        protected void onCreate(Bundle savedInstanceState) {
            super.onCreate(savedInstanceState);
            setContentView(R.layout.activity_main);
            s=(Button)findViewById(R.id.show);
            c=(Button)findViewById(R.id.count);
            r=(Button)findViewById(R.id.reverse);
            show=(TextView)findViewById(R.id.text1);
            str1=(EditText)findViewById(R.id.edittext1);
            s.setOnClickListener(new View.OnClickListener() {
                @Override
                public void onClick(View v) {
                    String s=str1.getText().toString();
                    show.setText(s);
                }
            });
            c.setOnClickListener(new View.OnClickListener() {
                @Override
                public void onClick(View v) {
                    String s=str1.getText().toString();
                    int n=s.length();
                    Toast.makeText(MainActivity.this, n+"", Toast.LENGTH_LONG).show();
                }
            });
            r.setOnClickListener(new View.OnClickListener() {
                @Override
                public void onClick(View v) {
                    String s=str1.getText().toString();
                    String revstr=new StringBuffer(s).reverse().toString();
                    show.setText(revstr);
                }
            });
        }
    }

