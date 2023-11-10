| 🐻 | DATA MAHASISWA |
| -------- | --- |
| **Nama** | Wisnu Ikhwansyah Saputra|
| **NIM** | 312010305 |
| **Kelas** | TI.22.A3 |
| **Mata Kuliah** | Pemrograman Mobile |

---

Soalnya adalah dari project sebelumnya Toast number dan Buatlah Method Program java
Toast Number, dengan menghasilkan Bilangan Fibonacci

```0, 1, 1, 2, 3,```


## Menambahkan Kodingan Java

ini adalah kodingan utama untuk menjalankan program bilangan fibonacci

    package com.hellotoast;
    
    import android.os.Bundle;
    import android.view.View;
    import android.widget.EditText;
    import android.widget.TextView;
    import android.widget.Toast;
    
    import androidx.appcompat.app.AppCompatActivity;

    public class MainToast extends AppCompatActivity {
    private TextView showCount;
    private int count = 0;
    private long fibNMinus1 = 1;
    private long fibNMinus2 = 0;
    private EditText edit_max_fibonacci;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_toast);

        showCount = findViewById(R.id.show_count);
        edit_max_fibonacci = findViewById(R.id.edit_max_fibonacci);

        updateCountDisplay();

        fibNMinus1 = 0;
        fibNMinus2 = 1;
    }

    private void updateCountDisplay() {
        showCount.setText(String.valueOf(fibNMinus2));

        if (count % 4 == 0) {
            showCount.setTextColor(getResources().getColor(R.color.colorPrimary));
        } else if (count % 4 == 1) {
            showCount.setTextColor(getResources().getColor(R.color.colorAccent));
        } else if (count % 4 == 2) {
            showCount.setTextColor(getResources().getColor(R.color.colorPrimary));
        } else {
            showCount.setTextColor(getResources().getColor(R.color.colorAccent));
        }
    }

    public void showToast(View view){
        Toast.makeText(this, "Bilangan Fibonacci",
                Toast.LENGTH_SHORT).show();
    }

    public void countUp(View view) {
        int maxFibonacci = Integer.parseInt(edit_max_fibonacci.getText().toString());

        if (count >= maxFibonacci) {
            Toast.makeText(this, "Maksimum Fibonacci tercapai", Toast.LENGTH_SHORT).show();
            return;
        }

        long fibCurrent;
        if (count == 0 || count == 0) {
            fibCurrent = 1;
        } else {
            fibCurrent = fibNMinus1 + fibNMinus2;
        }

        fibNMinus2 = fibNMinus1;
        fibNMinus1 = fibCurrent;
        updateCountDisplay();

        count++;
    }

    public void back1(View view) {
        count = 1;
        fibNMinus1 = 1;
        fibNMinus2 = 0;
        updateCountDisplay();
    }
    }

## output
### Tampilan Home

<img width="960" alt="Screenshot 2023-11-10 103928" src="https://github.com/Wizzs1/UTS-Pemrograman-Mobile/assets/110619093/af4ea685-2eab-42c2-9aaf-57644fdf95d5">

### Tampilan Fibonacci

<img width="960" alt="Screenshot 2023-11-10 103944" src="https://github.com/Wizzs1/UTS-Pemrograman-Mobile/assets/110619093/378a2bc9-2a73-43bf-afd5-4f6af0e40b70">

<img width="960" alt="Screenshot 2023-11-10 103956" src="https://github.com/Wizzs1/UTS-Pemrograman-Mobile/assets/110619093/24d07902-0089-4af1-8025-c689afa41610">

<img width="960" alt="Screenshot 2023-11-10 104007" src="https://github.com/Wizzs1/UTS-Pemrograman-Mobile/assets/110619093/6c107da1-1649-4f31-8b51-9c50e9b2ba96">

<img width="960" alt="Screenshot 2023-11-10 104021" src="https://github.com/Wizzs1/UTS-Pemrograman-Mobile/assets/110619093/ca8982e2-61b3-41ae-89d6-f288cb074573">

<img width="960" alt="Screenshot 2023-11-10 104030" src="https://github.com/Wizzs1/UTS-Pemrograman-Mobile/assets/110619093/a71bc9f4-5714-4f83-a873-678ac14a8484">

### Tampilan saat mencapai maks Fibonacci

<img width="960" alt="tampilan maksimal" src="https://github.com/Wizzs1/UTS-Pemrograman-Mobile/assets/110619093/259a432f-d760-48a7-ba6d-c591536d6983">
