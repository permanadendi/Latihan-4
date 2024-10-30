# Latihan-4

## Profil

| Variable        | Isi                         |
| --------------- | --------------------------- |
| **Nama**        | Dendi Permana               |
| **NIM**         | 312310694                   |
| **Kelas**       | TI.23.A.6                   |
| **Mata Kuliah** | Pemrograman Orientasi Objek |

### Latihan

File Bangun Datar

    abstract class BangunDatar {
        // Abstract methods Untuk area dan perimeter
        public abstract float luas();
        public abstract float keliling();
    }

File Lingkaran

    class Lingkaran extends BangunDatar {
        private int r;

        public Lingkaran(int r) {
            this.r = r;
        }

        @Override
        public float luas() {
            return (float) (Math.PI * r * r);
        }

        @Override
        public float keliling() {
            return (float) (2 * Math.PI * r);
        }
    }

File Segitiga

    class Segitiga extends BangunDatar {
        private int alas;
        private int tinggi;

        public Segitiga(int alas, int tinggi) {
            this.alas = alas;
            this.tinggi = tinggi;
        }

        @Override
        public float luas() {
            return (float) (0.5 * alas * tinggi);
        }

        @Override
        public float keliling() {

            return (float) (3 * alas);
        }
    }

File Persegi

    class Persegi extends BangunDatar {
        private int sisi;

        public Persegi(int sisi) {
            this.sisi = sisi;
        }

        @Override
        public float luas() {
            return sisi * sisi;
        }

        @Override
        public float keliling() {
            return 4 * sisi;
        }
    }

File Utama/Main

    public class Utama {
        public static void main(String[] args) {
            // Polimorfisme: Menggunakan referensi BangunDatar
            BangunDatar[] shapes = {
                new Lingkaran(7),
                new Segitiga(5, 10),
                new Persegi(4)
            };

            // Lakukan pengulangan pada setiap bentuk dan cetak nama, luas, dan kelilingnya
            for (BangunDatar shape : shapes) {
                if (shape instanceof Lingkaran) {
                    System.out.println("Lingkaran");
                } else if (shape instanceof Segitiga) {
                    System.out.println("Segitiga");
                } else if (shape instanceof Persegi) {
                    System.out.println("Persegi");
                }

                System.out.println("luas = " + shape.luas());
                System.out.println("keliling = " + shape.keliling());
                System.out.println(); // Untuk Spasi
            }
        }
    }

#### Output
