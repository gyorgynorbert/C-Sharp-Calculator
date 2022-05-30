# Alapszintű számológép
## Leírás
Egy alapszintű számológép, amely képes összeadásra, kivonásra, osztásra, szorzásra és az aktuális műveletek törlésére.

---

## Alap változók
```cs
        string bemenet = "0";
        string szam1 = "0";
        string szam2 = "0";
        string joperator = "";
```

- A "bemenet" tárolja a számológépen leütött számok értékét.
- A "szam1" és "szam2" tárolja készen levő számokat a műveletekre.
- a "joperator" tárolja a műveletünk fajtáját.
 
---

## Számok kezelése
```cs
        private void btn_two_Click_1(object sender, EventArgs e)
        {
            if (bemenet != "0")
            {
                bemenet = bemenet + "2";
            }
            else
            {
                bemenet = "2";
            }
            this.result.Text = "";
            this.result.Text += bemenet;
        }
```
Minden számra megnézzük először, hogy nulla-e. Ha nulla, akkor a bemenetet egyenlővé tesszük a bemeneti számmal (1, 2, stb.), viszont ha nem nulla, akkor az aktuális bemenetet egyenlővé tesszük a bemenettel plusz a bemeneti számmal. Ezek után az eredménydobozt kiüresítjük, majd beleírjuk a bemeneti számot.

---

## Operátorok kezelése
```cs
        private void btn_plus_Click(object sender, EventArgs e)
        {
            szam1 = bemenet;
            bemenet = "0";
            this.result.Text = "";
            joperator = "+";
        }
```
Először elraktározzuk a végső bementi számunkat egy változóban, majd a bemeneti változót kiürítjük. Utána az eredménydobozt is kiürítjük, végül a műveletjelölő operátorunknak értéket adunk műveletnek megfelelően (+, -, /, *)

---

## Az eredmény számolása

```cs
        private void button_equals_Click(object sender, EventArgs e)
        {
            szam2 = bemenet;
            if(joperator != "")
            {
                double n1, n2, eredmeny;
                try
                {
                    double.TryParse(szam1, out n1);
                    double.TryParse(szam2, out n2);
                    switch(joperator)
                    {
                        case "+":
                            this.result.Text = "";
                            eredmeny = n1 + n2;
                            this.result.Text = eredmeny.ToString();
                            n1 = eredmeny;
                            n2 = 0;
                            break;
                        case "-":
                            this.result.Text = "";
                            eredmeny = n1 - n2;
                            this.result.Text = eredmeny.ToString();
                            n1 = eredmeny;
                            n2 = 0;
                            break;
                        case "*":
                            this.result.Text = "";
                            eredmeny = n1 * n2;
                            this.result.Text = eredmeny.ToString();
                            n1 = eredmeny;
                            n2 = 0;
                            break;
                        case "/":
                            this.result.Text = "";
                            eredmeny = n1 / n2;
                            this.result.Text = eredmeny.ToString();
                            n1 = eredmeny;
                            n2 = 0;
                            break;
                    }
                }
                catch
                {
                    this.result.Text = "HIBA!";
                    bemenet = "";
                    szam1 = "";
                    szam2 = "";
                    joperator = "";
                }
            }
        }
```

Első sorban deklarálunk 3 segédváltozót, amit a későbbiek során használni fogunk. Ez után egy nagy try-catch-ben értéket adunk a segédváltozóinknak, majd ezután egy switch-ben megnézzük a műveletünk fajtáját. A művelet fajtájától függően elvégezzük a műveletet az "eredmeny" nevű változóba. Művelettől függetlenül kiürítjük az eredménydobozunkat, majd kiírjuk belé az eredményünket.

---

## Forráskód
```cs
using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace Gyorgy_Norbert_Projekt
{
    public partial class Calculator : Form
    {
        public Calculator()
        {
            InitializeComponent();
        }
        string bemenet = "0";
        string szam1 = "0";
        string szam2 = "0";
        string joperator = "";

        private void btn_zero_Click(object sender, EventArgs e)
        {
            if (bemenet != "0")
            {
                bemenet = bemenet + "0";
            }
            else
            {
                bemenet = "0";
            }
            this.result.Text = "";
            this.result.Text += bemenet;
        }

        private void btn_one_Click(object sender, EventArgs e)
        {
            if (bemenet != "0")
            {
                bemenet = bemenet + "1";
            }
            else
            {
                bemenet = "1";
            }
            this.result.Text = "";
            this.result.Text += bemenet;
        }

        private void btn_two_Click_1(object sender, EventArgs e)
        {
            if (bemenet != "0")
            {
                bemenet = bemenet + "2";
            }
            else
            {
                bemenet = "2";
            }
            this.result.Text = "";
            this.result.Text += bemenet;
        }

        private void btn_three_Click_1(object sender, EventArgs e)
        {
            if (bemenet != "0")
            {
                bemenet = bemenet + "3";
            }
            else
            {
                bemenet = "3";
            }
            this.result.Text = "";
            this.result.Text += bemenet;
        }
        private void btn_four_Click(object sender, EventArgs e)
        {
            if (bemenet != "0")
            {
                bemenet = bemenet + "4";
            }
            else
            {
                bemenet = "4";
            }
            this.result.Text = "";
            this.result.Text += bemenet;
        }
        private void btn_five_Click_1(object sender, EventArgs e)
        {
            result.Text = "Asd";
            if (bemenet != "0")
            {
                bemenet = bemenet + "5";
                result.Text = "asd";
            }
            else
            {
                bemenet = "5";
                result.Text = "asd";
            }
            this.result.Text = "";
            this.result.Text += bemenet;
        }
        private void btn_six_Click(object sender, EventArgs e)
        {
            if (bemenet != "0")
            {
                bemenet = bemenet + "6";
            }
            else
            {
                bemenet = "6";
            }
            this.result.Text = "";
            this.result.Text += bemenet;
        }
        private void btn_seven_Click_1(object sender, EventArgs e)
        {
            if (bemenet != "0")
            {
                bemenet = bemenet + "7";
            }
            else
            {
                bemenet = "7";
            }
            this.result.Text = "";
            this.result.Text += bemenet;
        }
        private void btn_eight_Click_1(object sender, EventArgs e)
        {
            if (bemenet != "0")
            {
                bemenet = bemenet + "8";
            }
            else
            {
                bemenet = "8";
            }
            this.result.Text = "";
            this.result.Text += bemenet;
        }

        private void btn_nine_Click(object sender, EventArgs e)
        {
            if (bemenet != "0")
            {
                bemenet = bemenet + "9";
            }
            else
            {
                bemenet = "9";
            }
            this.result.Text = "";
            this.result.Text += bemenet;
        }

        private void btn_plus_Click(object sender, EventArgs e)
        {
            szam1 = bemenet;
            bemenet = "0";
            this.result.Text = "";
            joperator = "+";
        }

        private void btn_minus_Click(object sender, EventArgs e)
        {
            szam1 = bemenet;
            bemenet = "0";
            this.result.Text = "";
            joperator = "-";
        }

        private void btn_times_Click(object sender, EventArgs e)
        {
            szam1 = bemenet;
            bemenet = "0";
            this.result.Text = "";
            joperator = "*";
        }

        private void btn_divide_Click(object sender, EventArgs e)
        {
            szam1 = bemenet;
            bemenet = "0";
            this.result.Text = "";
            joperator = "/";
        }

        private void button_equals_Click(object sender, EventArgs e)
        {
            szam2 = bemenet;
            if(joperator != "")
            {
                double n1, n2, eredmeny;
                try
                {
                    double.TryParse(szam1, out n1);
                    double.TryParse(szam2, out n2);
                    switch(joperator)
                    {
                        case "+":
                            this.result.Text = "";
                            eredmeny = n1 + n2;
                            this.result.Text = eredmeny.ToString();
                            n1 = eredmeny;
                            n2 = 0;
                            break;
                        case "-":
                            this.result.Text = "";
                            eredmeny = n1 - n2;
                            this.result.Text = eredmeny.ToString();
                            n1 = eredmeny;
                            n2 = 0;
                            break;
                        case "*":
                            this.result.Text = "";
                            eredmeny = n1 * n2;
                            this.result.Text = eredmeny.ToString();
                            n1 = eredmeny;
                            n2 = 0;
                            break;
                        case "/":
                            this.result.Text = "";
                            eredmeny = n1 / n2;
                            this.result.Text = eredmeny.ToString();
                            n1 = eredmeny;
                            n2 = 0;
                            break;
                    }
                }
                catch
                {
                    this.result.Text = "HIBA!";
                    bemenet = "";
                    szam1 = "";
                    szam2 = "";
                    joperator = "";
                }
            }
        }

        private void btn_clear_Click(object sender, EventArgs e)
        {
            bemenet = "";
            szam1 = "";
            szam2 = "";
            joperator = "";
            this.result.Text = "";
        }


    }
}

```
