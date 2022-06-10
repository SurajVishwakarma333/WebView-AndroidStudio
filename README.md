# WebView-AndroidStudio
In Android, WebView is a view used to display the web pages in application. 

This class is the basis upon which you can roll your own web browser or simply use it to display some online content within your Activity.

Basically, WebView turns application into a web application.

# Steps 
1. Add internet permission in manifest file.
             <uses-permission android:name="android.permission.INTERNET"/>
             
2. .xml file.

          <?xml version="1.0" encoding="utf-8"?>
          <androidx.constraintlayout.widget.ConstraintLayout
             xmlns:android="http://schemas.android.com/apk/res/android"
             xmlns:app="http://schemas.android.com/apk/res-auto"
             xmlns:tools="http://schemas.android.com/tools"
             android:layout_width="match_parent"
             android:layout_height="match_parent"
             tools:context=".MainActivity">
    
            <EditText
              android:id="@+id/editText"
              android:layout_width="351dp"
              android:layout_height="46dp"
              android:layout_marginTop="4dp"
              android:focusable="true"
              android:hint="Enter Text"
              app:layout_constraintEnd_toEndOf="parent"
              app:layout_constraintStart_toStartOf="parent"
              app:layout_constraintTop_toBottomOf="@+id/webView" />

            <WebView
              android:id="@+id/webView"
              android:layout_width="358dp"
              android:layout_height="574dp"
              app:layout_constraintEnd_toEndOf="parent"
              app:layout_constraintHorizontal_bias="1.0"
              app:layout_constraintStart_toStartOf="parent"
              app:layout_constraintTop_toTopOf="parent" />

            <Button
              android:id="@+id/button"
              android:layout_width="wrap_content"
              android:layout_height="wrap_content"
              android:layout_marginBottom="24dp"
              android:text="Load Web Page"
              app:layout_constraintBottom_toBottomOf="parent"
              app:layout_constraintEnd_toEndOf="parent"
              app:layout_constraintStart_toStartOf="parent"
              app:layout_constraintTop_toBottomOf="@+id/editText" />

        </androidx.constraintlayout.widget.ConstraintLayout>


