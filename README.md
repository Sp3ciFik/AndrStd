//# AndrStd
//Clicker
package com.example.pcp.clicker;

import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.TextView;

public class MainActivity extends AppCompatActivity {

    public int swap(int a, int b) {  // usage: y = swap(x, x=y);
        return a;
    }
    Button btnClick1,btnClick2,btnClick3;
    Button btnReset;
    Button btnSort;

    TextView txtCount1,txtCount2,txtCount3;


    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        // BTN 1
        btnSort= (Button)findViewById(R.id.buttonSort);
        btnClick1 = (Button)findViewById(R.id.buttonClick1);
        txtCount1 = (TextView)findViewById(R.id.textViewCount1);
        btnClick1.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                String countValue= txtCount1.getText().toString();
                btnSort.setVisibility(View.VISIBLE);
                int intCountValue = Integer.parseInt(countValue);

                intCountValue++;

                txtCount1.setText(String.valueOf(intCountValue));
            }
        });

        // BTN 2

        btnClick2 = (Button)findViewById(R.id.buttonClick2);
        txtCount2 = (TextView)findViewById(R.id.textViewCount2);
        btnClick2.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                String countValue= txtCount2.getText().toString();
                btnSort.setVisibility(View.VISIBLE);
                int intCountValue = Integer.parseInt(countValue);

                intCountValue++;

                txtCount2.setText(String.valueOf(intCountValue));
            }
        });

        // BTN 3

        btnClick3 = (Button)findViewById(R.id.buttonClick3);
        txtCount3 = (TextView)findViewById(R.id.textViewCount3);
        btnClick3.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                String countValue= txtCount3.getText().toString();
                btnSort.setVisibility(View.VISIBLE);
                int intCountValue = Integer.parseInt(countValue);

                intCountValue++;

                txtCount3.setText(String.valueOf(intCountValue));
            }
        });

        // BTN  RESET

        btnReset = (Button)findViewById(R.id.buttonReset);
        btnReset.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                String countValue1= txtCount1.getText().toString();
                String countValue2= txtCount2.getText().toString();
                String countValue3= txtCount3.getText().toString();

                btnSort.setVisibility(View.VISIBLE);

                int intCountValue1 = Integer.parseInt(countValue1);
                int intCountValue2 = Integer.parseInt(countValue2);
                int intCountValue3 = Integer.parseInt(countValue3);

                intCountValue1=0;
                intCountValue2=0;
                intCountValue3=0;

                txtCount1.setText(String.valueOf(intCountValue1));
                txtCount2.setText(String.valueOf(intCountValue2));
                txtCount3.setText(String.valueOf(intCountValue3));
            }
        });

        //BTN SORT



        btnSort.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {

                btnSort.setVisibility(View.INVISIBLE);

                String countValue1= txtCount1.getText().toString();
                String countValue2= txtCount2.getText().toString();
                String countValue3= txtCount3.getText().toString();

                int intCountValue1 = Integer.parseInt(countValue1);
                int intCountValue2 = Integer.parseInt(countValue2);
                int intCountValue3 = Integer.parseInt(countValue3);

                int val1=intCountValue1;
                int val2=intCountValue2;
                int val3=intCountValue3;

                if(val1>=val2 && val1>=val3)
                {
                    if(val2>=val3)
                    {
                        val1=swap(val3,val3=val1);
                    }
                    else
                    {
                        val2=swap(val1,val1=val2);
                        val3=swap(val2,val2=val3);
                    }
                }
                else
                {
                    if(val2>=val1 && val2>=val3)
                    {
                        if(val1>=val3)
                        {
                            val3=swap(val1,val1=val3);
                            val3=swap(val2,val2=val3);
                        }
                        else
                        {
                            val3=swap(val2,val2=val3);
                        }
                    }
                    else
                    {
                        if(val3>=val1 && val3>=val2)
                        {
                            if(val1>=val2)
                            {
                                val2=swap(val1,val1=val2);
                            }
                        }
                    }

                }

                txtCount1.setText(String.valueOf(val1));
                txtCount2.setText(String.valueOf(val2));
                txtCount3.setText(String.valueOf(val3));

            }

        });
    }
}
