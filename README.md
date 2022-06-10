# WebView-AndroidStudio
In Android, WebView is a view used to display the web pages in application. 

This class is the basis upon which you can roll your own web browser or simply use it to display some online content within your Activity.

Basically, WebView turns application into a web application.

# Steps for Calling Dynamic Web in our Activity

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
        
        
3. .java file.



         import androidx.appcompat.app.AppCompatActivity;

         import android.os.Bundle;
         import android.view.View;
         import android.webkit.WebView;
         import android.webkit.WebViewClient;
         import android.widget.Button;
         import android.widget.EditText;

         public class MainActivity extends AppCompatActivity {

         private WebView webView;
         EditText edt;
         Button btn;

         @Override
         protected void onCreate(Bundle savedInstanceState) {
         super.onCreate(savedInstanceState);
         setContentView(R.layout.activity_main);

         btn=findViewById(R.id.button);
         edt=findViewById(R.id.editText);
         webView=findViewById(R.id.webView);
         webView.setWebViewClient(new MyBrowser());

         btn.setOnClickListener(new View.OnClickListener() {
                @Override
                public void onClick(View v) {
                String url = edt.getText().toString();  //for calling dynamic web means what we give link path of website that only it will display.
                //String url= "https://github.com/SurajVishwakarma333";  //for calling static web means what we provide/specified our own website link in our code that only it will display.
                  webView.getSettings().setLoadsImagesAutomatically(true);
                  webView.getSettings().setJavaScriptEnabled(true);
                  webView.setScrollBarStyle(View.SCROLLBARS_INSIDE_OVERLAY);
                  webView.loadUrl(url);
              }
           });
        }
        //If you click on any link inside the webpage of the WebView, that page will not be loaded inside your WebView. 
        //In order to do that you need to extend your class from WebViewClient and override its method. 
        private class MyBrowser extends WebViewClient {
              @Override
              public boolean shouldOverrideUrlLoading(WebView view, String url) {
                view.loadUrl(url);
                return true;
              }
        }
       }

https://user-images.githubusercontent.com/101108540/173015053-0d8c971c-71d0-4bef-b57c-fb52416277c9.mp4
