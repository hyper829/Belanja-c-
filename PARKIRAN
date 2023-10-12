#include <iostream>
#include <string>
#include <chrono>
#include <iomanip>
#include <vector>

using namespace std;
using namespace std::chrono;

struct Kendaraan {
    string jenis;
    string platNomer;
    steady_clock::time_point waktu;
};

int main() {
    char choice;
    vector<Kendaraan> data;
    vector<Kendaraan> datamobilkeluar;

    while (true) {
        cout << "Pilih Aksi:\n";
        cout << "1. Lihat Data Kendaraan\n";
        cout << "2. Kendaraan Masuk\n";
        cout << "3. Kendaraan Keluar\n"; // Ubah pilihan menjadi "Kendaraan Keluar".
        cout << "4. Keluar\n"; // Ganti pilihan "Keluar" menjadi pilihan ke-4.
        cout << "Masukkan pilihan (1/2/3/4): ";
        cin >> choice;

        switch (choice) {
            case '1':
                cout << "Data yang sudah masuk:\n";
                for (const Kendaraan& kendaraan : data) {
                    duration<double> elapsedSeconds = duration_cast<duration<double>>(steady_clock::now() - kendaraan.waktu);
                    cout << "Jenis Kendaraan: " << kendaraan.jenis << endl;
                    cout << "Plat Nomer: " << kendaraan.platNomer << endl;
                    cout << "Waktu sejak data dimasukkan: " << fixed << setprecision(2) << elapsedSeconds.count() << " detik" << endl;
                    cout << "----------------------\n";
                }
                break;

            case '2':
                {
                    Kendaraan kendaraan;
                    cout << "Masukan Jenis Kendaraan: ";
                    cin >> kendaraan.jenis;
                    cout << "Masukan Plat Nomer: ";
                    cin >> kendaraan.platNomer;
                    kendaraan.waktu = steady_clock::now();
                    data.push_back(kendaraan);
                    cout << "Anda Memasukkan Data" << endl;
                    cout << "Jenis Kendaraan: " << kendaraan.jenis << endl;
                    cout << "Plat Nomer: " << kendaraan.platNomer << endl;
                }
                break;

            case '3':
                {
                    cout << "Pilih data kendaraan yang keluar:\n";
                    for (size_t i = 0; i < data.size(); ++i) {
                        cout << i << ". Jenis Kendaraan: " << data[i].jenis << " - Plat Nomer: " << data[i].platNomer << endl;
                    }
                    int mobilkeluar;
                    cout << "Masukkan nomor kendaraan yang keluar dari parkiran: ";
                    cin >> mobilkeluar;

                    if (mobilkeluar >= 0 && mobilkeluar < data.size()) {
                        Kendaraan kendaraanKeluar = data[mobilkeluar];
                        duration<double> elapsedSeconds = duration_cast<duration<double>>(steady_clock::now() - kendaraanKeluar.waktu);
                        double durasiJam = elapsedSeconds.count() / 3600; // Hitung durasi dalam jam.

                        double biaya = 3000; // Biaya awal.

                        if (durasiJam > 1.0) {
                            biaya += (durasiJam - 1) * 3000; // Biaya tambahan jika lebih dari 1 jam.
                        }

                        cout << "Kendaraan Keluar: " << kendaraanKeluar.jenis << " - Plat Nomer: " << kendaraanKeluar.platNomer << endl;
                        cout << "Waktu parkir: " << fixed << setprecision(2) << durasiJam << " jam" << endl;
                        cout << "Biaya parkir: " << fixed << setprecision(2) << biaya << " IDR" << endl;
                        
                        datamobilkeluar.push_back(kendaraanKeluar); // Tambahkan kendaraan ke vektor yang telah keluar.
                        data.erase(data.begin() + mobilkeluar); // Hapus kendaraan dari vektor data utama.
                    } else {
                        cout << "Indeks kendaraan yang dimasukkan tidak valid.\n";
                    }
                }
                break;

            case '4':
                cout << "Kendaraan yang sudah keluar:\n";
                for (const Kendaraan& kendaraan : datamobilkeluar) {
                    cout << "Jenis Kendaraan: " << kendaraan.jenis << endl;
                    cout << "Plat Nomer: " << kendaraan.platNomer << endl;
                    cout << "----------------------\n";
                }
                cout << "Keluar dari program\n";
                return 0;

            default:
                cout << "Pilihan tidak valid\n";
                break;
        }
    }

    cout << "Terima kasih!";
    return 0;
}

