# SPINNER
Spinner allows you to select an item from a _drop down_ menu.
Android spinner is like the drop down menu with multiple values from which the end user can select only one value.
Android spinner is associated with **AdapterView**. So you need to use one of the **adapter classes** with spinner.
Android Spinner class is the subclass of AsbSpinner class.

### For Example

 <img src= "http://3.bp.blogspot.com/-d1pt2GTOZ-I/UjxbCVF-rlI/AAAAAAABGPc/Ed43IyMjGSo/s1600/android-spinner-style-01.PNG">
 
 ##### You might have seen this spinner in gmail app
 
 <img src= "https://www.tutorialspoint.com/android/images/spinner11.jpg">
 
 ## Let's understand Spinners with the help of an example :-
 
 #### In this example, we are going to display the country list. You need to use **ArrayAdapter** class to store the country list.
 
### _Activity_main.xml_ 

Drag the Spinner from the pallete, now the activity_main.xml file will like this:

```
<RelativeLayout xmlns:androclass="http://schemas.android.com/apk/res/android"  
    xmlns:tools="http://schemas.android.com/tools"  
    android:layout_width="match_parent"  
    android:layout_height="match_parent"  
    tools:context=".MainActivity" >  
  
    <Spinner  
        android:id="@+id/spinner1"  
        android:layout_width="wrap_content"  
        android:layout_height="wrap_content"  
        android:layout_alignParentTop="true"  
        android:layout_centerHorizontal="true"  
        android:layout_marginTop="83dp" />  
  
</RelativeLayout>
```
### Now Let's write the code to display item on the spinner and perform event handling.

## MainActivity.java 

```
package com.example.spinner;  
import android.app.Activity;  
import android.os.Bundle;  
import android.view.Menu;  
import android.view.View;  
import android.widget.AdapterView;  
import android.widget.ArrayAdapter;  
import android.widget.Spinner;  
import android.widget.TextView;  
import android.widget.Toast;  
  
public class MainActivity extends Activity implements  
AdapterView.OnItemSelectedListener {  
  
    String[] country = { "India", "USA", "China", "Japan", "Other",  };  
  
    @Override  
    protected void onCreate(Bundle savedInstanceState) {  
        super.onCreate(savedInstanceState);  
        setContentView(R.layout.activity_main);  
        //Getting the instance of Spinner and applying OnItemSelectedListener on it  
        Spinner spin = (Spinner) findViewById(R.id.spinner1);  
        spin.setOnItemSelectedListener(this);  
          
        //Creating the ArrayAdapter instance having the country list  
        ArrayAdapter aa = new ArrayAdapter(this,android.R.layout.simple_spinner_item,country);  
        aa.setDropDownViewResource(android.R.layout.simple_spinner_dropdown_item);  
        //Setting the ArrayAdapter data on the Spinner  
        spin.setAdapter(aa);  
    }  
  
      
    //Performing action onItemSelected and onNothing selected  
    @Override  
    public void onItemSelected(AdapterView<?> arg0, View arg1, int position,long id) {  
        Toast.makeText(getApplicationContext(),country[position] ,Toast.LENGTH_LONG).show();  
    }  
  
    @Override  
    public void onNothingSelected(AdapterView<?> arg0) {  
        // TODO Auto-generated method stub  
          
    }  
  
    @Override  
    public boolean onCreateOptionsMenu(Menu menu) {  
        // Inflate the menu; this adds items to the action bar if it is present.  
        getMenuInflater().inflate(R.menu.activity_main, menu);  
        return true;  
    }  
}  
```
## OUTPUT 

<img src="https://www.javatpoint.com/images/androidimages/spinneroutput1.png"> <img src="https://www.javatpoint.com/images/androidimages/spinneroutput2.png"> <img src="https://www.javatpoint.com/images/androidimages/spinneroutput3.png">
 
 
