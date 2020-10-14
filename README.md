# djp-json-response

Dokumen ini berisi panduan kepada developer di Direktorat Jenderal Pajak tentang standar response REST API baik pada service yang diberikan DJP ke pihak eksternal maupun pihak internal DJP sendiri.

Panduan ini merujuk pada standar Jsend yang dikembangkan oleh Omniti Labs (https://github.com/omniti-labs/jsend/) dengan penyesuaian.

Contoh Response API yang sesuai dengan panduan ini dapat digambarkan sebagai berikut:
```
{
  status : "success",
  data : {
    "post" : { "id" : 1, "title" : "Judul Dokumen", "body" : "Isi Dokumen." }
  }
}
```

Standar JSON response

<table>
<tr><th>status</td><th>Description</th><th>Properti Yang Harus Ada</th><th>Properti Opsional</td></tr>
<tr><td>success</td><td>Semua berjalan dengan baik, dan (biasanya) ada data yang dikembalikan.</td><td>status, data</td><td></td></tr>
<tr><td>fail</td><td>Ada masalah pada data input dari klien.</td><td>status, data</td><td></td></tr>
<tr><td>error</td><td>Ada masalah pada pemrosesan data.</td><td>status, message</td><td>code, data</td></tr>
</table>
