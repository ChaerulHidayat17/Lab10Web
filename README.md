# Pratikum 10

# 1. buat file dengan nama **mobil.php** yang berisi code di bawah ini <br>

    <?php
    // Program sederhana pemanggilan class

    class Mobil {
        private $warna;
        private $merk;
        private $harga;

        public function __construct() {
            $this->warna = "Biru";
            $this->merk = "Porsche";
            $this->harga = "10000000";
        }

        public function gantiWarna($warnaBaru) {
            $this->warna = $warnaBaru;
        }

        public function tampilWarna() {
            echo "Warna mobil : ".$this->warna;
        }
    }

    // Objek mobil
    $a = new Mobil();
    $b = new Mobil();

    // Memanggil objek
    echo "<b>Mobil pertama<b><br>";
    $a->tampilWarna();
    echo "<br>Mobil pertama ganti warna<br>";
    $a->gantiWarna('Merah');
    $a->tampilWarna();

    echo "<br><b>Mobil kedua</b><br>";
    $b->gantiWarna('Hijau');
    $b->tampilWarna();

    ?>

<br>
#2. Kita buat file dengan nama **form.php** dengan code seperti di bawah <br>

    <?php

    class Form {
        private $fields = array();
        private $action;
        private $submit = "Submit Form";
        private $jumField = 0;

        public function __construct($action, $submit) {
            $this->action = $action;
            $this->submit = $submit;
        }

        public function displayForm() {
            echo "<form action='".$this->action."' method='POST'>";
            echo '<table width="100%" border="0">';
            for ($j=0; $j<count($this->fields); $j++) {
            echo "<tr><td
            align='right'>".$this->fields[$j]['label']."</td>";
            echo "<td><input type='text'
            name='".$this->fields[$j]['name']."'></td></tr>";
            }
            echo "<tr><td colspan='2'>";
            echo "<input type='submit' value='".$this->submit."'></td></tr>";
            echo "</table>";
        }

        public function addField($name, $label) {
            $this->fields [$this->jumField]["name"] = $name;
            $this->fields [$this->jumField]["label"] = $label;
            $this->jumField++;
        }
    }
    ?>

<br>
