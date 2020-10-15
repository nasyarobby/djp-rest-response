# djp-json-response

Dokumen ini berisi panduan kepada developer di Direktorat Jenderal Pajak tentang standar response REST API baik pada service yang diberikan DJP ke pihak eksternal maupun pihak internal DJP sendiri.

Panduan ini merujuk pada standar Jsend yang dikembangkan oleh Omniti Labs (https://github.com/omniti-labs/jsend/) dengan penyesuaian.

Contoh Response API yang sesuai dengan panduan ini dapat digambarkan sebagai berikut:

```
{
  status : "success",
  message: "Dokumen berhasil diambil."
  result : {
    "post" : { "id" : 1, "title" : "Judul Dokumen", "body" : "Isi Dokumen." }
  }
}
```

Standar JSON response

<table>
<tr><th>status</td><th>Deskripsi</th><th>Properti Yang Harus Ada</th><th>Properti Opsional</td></tr>
<tr><td>success</td><td>Semua berjalan dengan baik, dan (biasanya) ada data yang dikembalikan.</td><td>status, result</td><td>message</td></tr>
<tr><td>fail</td><td>Ada masalah pada data input dari klien.</td><td>status, result, message</td><td></td></tr>
<tr><td>error</td><td>Ada masalah pada pemrosesan data.</td><td>status, message</td><td>error</td></tr>
</table>

## Response status success

Response dengan status success berjalan sesuai dengan tujuan request dikirimkan.

<table>
<tr><th>Properti</th><th>Tipe</th><th>Keterangan</th></tr>
<tr><td>status</td><td>String</td><td>HARUS bernilai "success"</td></tr>
<tr><td>message</td><td>String</td><td>Teks pesan hasil response. Misal: "Data berhasil diambil".</td></tr>
<tr><td>result</td><td>Object | null</td><td>Data balikan</td></tr>
</table>

## Response status fail

<table>
<tr><th>Properti</th><th>Tipe</th><th>Keterangan</th></tr>
<tr><td>status</td><td>String</td><td>HARUS bernilai "fail"</td></tr>
<tr><td>message</td><td>String</td><td>Teks pesan kesalahan secara umum. Misal: "Autentikasi gagal.".</td></tr>
<tr><td>result</td><td>Object</td><td>Data balikan berupa object dengan properti parameter key dengan isi pesan kesalahan.</td></tr>
</table>

## Response status error

<table>
<tr><th>Properti</th><th>Tipe</th><th>Keterangan</th></tr>
<tr><td>status</td><td>String</td><td>HARUS bernilai "error"</td></tr>
<tr><td>message</td><td>String</td><td>Teks pesan kesalahan. Misal: "Tidak berhasil terhubung ke database.".</td></tr>
<tr><td>error</td><td>Object</td><td>Object berisi informasi mengenai error. </td></tr>
</table>
