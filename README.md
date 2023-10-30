| Nama       | Faris Syahluthfi               |
| ---------- | ------------------------------ |
| NIM        | 312010034                      |
| Kelas      | TI.20.RPL-1                    |
| Mata Kuliah| Pemrograman Visual             |
| Dosen      | Agung Nugroho, S.Kom., M.Kom.  |

## Latihan
# 1. Program Menghitung Gaji Karyawan

<li>Tampilan Utama Program</li></br>

![Utama](Gambar/Utama.png)</p>

<li>Menghitung Gaji Bersih Direktur Tetap</li></br>

![Direktur Tetap](Gambar/Direktur%20Tetap.png)</p>

<li>Menghitung Gaji Bersih Manager Tetap</li></br>

![Manager Tetap](Gambar/Manager%20Tetap.png)</p>

<li>Menghitung Gaji Bersih Karyawan Tetap</li></br>

![Karyawan Tetap](Gambar/Karyawan%20Tetap.png)</p>

<li>Menghitung Gaji Bersih Direktur Honorer</li></br>

![Direktur Honorer](Gambar/Direktur%20Honorer.png)</p>

<li>Menghitung Gaji Bersih Manager Honorer</li></br>

![Manager Honorer](Gambar/Manager%20Honorer.png)</p>

<li>Menghitung Gaji Bersih Karyawan Honorer</li></br>

![Karyawan Honorer](Gambar/Karyawan%20Honorer.png)</p>

<li>Source Code Menghitung Gaji Bersih</li></br>

```pascal

procedure TForm1.btnHitungClick(Sender: TObject);
var
  GajiPokok, TotalGaji, GajiBersih: Double;
  StatusTunjangan: Double;


begin
  GajiPokok := StrToFloat(edtGapok.Text);
  StatusTunjangan := StrToFloat(edtTunjangan.Text);

  TotalGaji := GajiPokok + StatusTunjangan;

  GajiBersih := TotalGaji;

  edtTotalGaji.Text := FormatFloat('#,##0.00', TotalGaji);

end;              

```

<li>Source code Gaji Pokok Otomatis Sesuai Dengan Jabatan</li></br>

```pascal

procedure TForm1.cbJabatanChange(Sender: TObject);
var
  Jabatan: string;
  GajiPokok: Double;

begin
  Jabatan := cbJabatan.Items[cbJabatan.ItemIndex];

  case Jabatan of
    'Direktur': GajiPokok := 5000000;
    'Manager': GajiPokok := 3000000;
    'Karyawan': GajiPokok := 1000000;
  else
    GajiPokok := 0; // Nilai default jika jabatan tidak ada
  end;

  edtGapok.Text := FloatToStr(GajiPokok);
end;

end.     


```

<li>Source code Status Tunjangan Otomatis Sesuai Dengan Status</li></br>

```pascal

procedure TForm1.rbHonorerChange(Sender: TObject);
begin
  if rbHonorer.Checked then
    edtTunjangan.Caption := '500000';

end;

procedure TForm1.rbTetapChange(Sender: TObject);
begin
  if rbTetap.Checked then
    edtTunjangan.Caption := '1500000';
end; 


```

