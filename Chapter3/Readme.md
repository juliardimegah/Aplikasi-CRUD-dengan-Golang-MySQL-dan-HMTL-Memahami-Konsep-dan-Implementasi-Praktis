# BAB 3
# MEMBUAT HALAMAN TAMPILAN (FRONTEND)

## 3.1 Membuat Tampilan HTML Home
Dalam pengembangan aplikasi CRUD, kita perlu mengembangkan tampilan untuk mengakses apa yang akan dikembangkan pada sisi backend. Yang akan kita buat pertama kali dari sisi frontend adalah home yang bernama index.html yang akan diletakan dalam folder views/home.
1. Buatlah struktur dasar HTML.
```
 <!DOCTYPE html>
<html>
<head>
  <title>Judul Halaman</title>
</head>
<body>
	…
</body>
</html>
```

2. Ambil struktur untuk membuat tampilan menggunakan Bootstrap

```
<meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Bootstrap demo</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-rbsA2VBKQhggwzxH7pPCaAqO46MgnOM80zW1RWuH61DGLwZJEdK2Kadq2F9CUG65" crossorigin="anonymous">
```

Struktur diatas akan dimasukan pada bagian <head>, sehingga tampilannya akan seperti berikut:

```
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Bootstrap demo</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-rbsA2VBKQhggwzxH7pPCaAqO46MgnOM80zW1RWuH61DGLwZJEdK2Kadq2F9CUG65" crossorigin="anonymous">

</head>
<body>
	…
</body>
</html>

```

3. Ambilah contoh struktur untuk membuat navbar dari dokumentasi pada web Bootstrap seperti berikut:
```
    <nav class="navbar navbar-expand-lg bg-dark">
      <div class="container">
        <a class="navbar-brand text-light" href="/">Go Products</a>
        <button
          class="navbar-toggler"
          type="button"
          data-bs-toggle="collapse"
          data-bs-target="#navbarNav"
          aria-controls="navbarNav"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav ms-auto">
            <li class="nav-item pe-3">
              <a
                class="nav-link active text-light"
                aria-current="page"
                href="/products"
                >Products</a
              >
            </li>
            <li class="nav-item">
              <a class="nav-link active text-light" href="/categories"
                >Categories</a
              >
            </li>
          </ul>
        </div>
      </div>
    </nav>
```

Sehingga struktur keseluruhan akan jadi seperti ini:

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>GO Products</title>
    <link
      href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/css/bootstrap.min.css"
      rel="stylesheet"
      integrity="sha384-GLhlTQ8iRABdZLl6O3oVMWSktQOp6b7In1Zl3/Jr59b6EGGoI1aFkw7cmDA6j6gD"
      crossorigin="anonymous"
    />
  </head>
  <body>
    <!-- Navar -->
    <nav class="navbar navbar-expand-lg bg-dark">
      <div class="container">
        <a class="navbar-brand text-light" href="/">Go Products</a>
        <button
          class="navbar-toggler"
          type="button"
          data-bs-toggle="collapse"
          data-bs-target="#navbarNav"
          aria-controls="navbarNav"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav ms-auto">
            <li class="nav-item pe-3">
              <a
                class="nav-link active text-light"
                aria-current="page"
                href="/products"
                >Products</a
              >
            </li>
            <li class="nav-item">
              <a class="nav-link active text-light" href="/categories"
                >Categories</a
              >
            </li>
          </ul>
        </div>
      </div>
    </nav>
    <!-- End of Navbar -->

    <div class="container mt-3">
      <h1>Hello, world!</h1>
    </div>
  </body>
</html>
```

Dengan struktur diatas tampilan pada Home telah selesai kita buat. Selanjutnya kita buat tampilan frontend lainnya dengan memodifikasi tampilan diatas.

## 3.2 Membuat Tampilan HTML Home Category
Untuk tampilan Home dari bagian Category kita perlu memodifikasi bagian body dari tampilan home yang ada pada index.html yang ada pada views/home. Setelah diubah kita hanya perlu memindahkan file index.html untuk bagian category ke views/category. Berikut langkah – langkahnya:
1. Bukalah file index.html yang tadi kita buat untuk views/home. Lalu kita ubah bagian bodynya dengan menyesuaikan dengan kebutuhan. Sebagai contoh kita buat tabel seperti berikut dengan memanfaatkan js untuk membuat baris baru dari setiap baris data yang ada pada database:
```
<div class="container mt-3">
      <h2>List Categories</h2>
      <hr />
      <a href="/categories/add" class="btn btn-primary">Add Categories</a>
      <table class="table table-bordered mt-2 text-center">
        <thead>
          <tr>
            <th>Name</th>
            <th>Action</th>
          </tr>
        </thead>
        <tbody>
          {{range .categories}}
          <tr>
            <td>{{.Name}}</td>
            <td>
              <a
                href="/categories/edit?id={{.Id}}"
                class="btn btn-sm btn-warning text-light"
                >Edit</a
              >
              <a
                href="/categories/delete?id={{.Id}}"
                onclick="return confirm('Are you sure want to delete this category ?')"
                class="btn btn-sm btn-danger"
                >Delete</a
              >
            </td>
          </tr>
          {{end}}
        </tbody>
      </table>
    </div>

```

Sehingga struktur kodenya jadi seperti berikut:

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>GO Products</title>
    <link
      href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/css/bootstrap.min.css"
      rel="stylesheet"
      integrity="sha384-GLhlTQ8iRABdZLl6O3oVMWSktQOp6b7In1Zl3/Jr59b6EGGoI1aFkw7cmDA6j6gD"
      crossorigin="anonymous"
    />
  </head>
  <body>
    <!-- Navar -->
    <nav class="navbar navbar-expand-lg bg-dark">
      <div class="container">
        <a class="navbar-brand text-light" href="/">Go Products</a>
        <button
          class="navbar-toggler"
          type="button"
          data-bs-toggle="collapse"
          data-bs-target="#navbarNav"
          aria-controls="navbarNav"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav ms-auto">
            <li class="nav-item pe-3">
              <a
                class="nav-link active text-light"
                aria-current="page"
                href="/products"
                >Products</a
              >
            </li>
            <li class="nav-item">
              <a class="nav-link active text-light" href="/categories"
                >Categories</a
              >
            </li>
          </ul>
        </div>
      </div>
    </nav>
    <!-- End of Navbar -->

    <div class="container mt-3">
      <h2>List Categories</h2>
      <hr />
      <a href="/categories/add" class="btn btn-primary">Add Categories</a>
      <table class="table table-bordered mt-2 text-center">
        <thead>
          <tr>
            <th>Name</th>
            <th>Action</th>
          </tr>
        </thead>
        <tbody>
          {{range .categories}}
          <tr>
            <td>{{.Name}}</td>
            <td>
              <a
                href="/categories/edit?id={{.Id}}"
                class="btn btn-sm btn-warning text-light"
                >Edit</a
              >
              <a
                href="/categories/delete?id={{.Id}}"
                onclick="return confirm('Are you sure want to delete this category ?')"
                class="btn btn-sm btn-danger"
                >Delete</a
              >
            </td>
          </tr>
          {{end}}
        </tbody>
      </table>
    </div>
  </body>
</html>
```

## 3.3 Membuat Tampilan HTML Create Category
Untuk tampilan Edit dari bagian Category kita perlu memodifikasi bagian body dari tampilan home yang ada pada index.html yang ada pada views/home. Setelah diubah kita hanya perlu mengganti nama file index.html menjadi create.html dan disimpan ke views/category. Berikut langkah – langkahnya:
1. Bukalah file index.html yang tadi kita buat untuk views/home. Lalu kita ubah bagian bodynya dengan menyesuaikan dengan kebutuhan. Sebagai contoh kita buat tabel seperti berikut dengan memanfaatkan js untuk membuat form input data kategori baru:
```
<DIV CLASS="CONTAINER MT-3">
      <DIV CLASS="ROW D-FLEX JUSTIFY-CONTENT-CENTER">
        <DIV CLASS="COL-4">
          <H2>ADD CATEGORY</H2>
          <HR />

          <FORM ACTION="/CATEGORIES/ADD" METHOD="POST">
            <DIV CLASS="MB-3">
              <LABEL CLASS="FORM-LABEL">NAME</LABEL>
              <INPUT
                type="text"
                class="form-control"
                name="name"
                autocomplete="off"
              />
            </div>
            <div class="float-end">
              <a href="/categories" class="btn btn-secondary">Back</a>
              <button type="submit" class="btn btn-primary">Save</button>
            </div>
          </form>
        </div>
      </div>
    </div>
```

Sehingga struktur kodenya jadi seperti berikut :

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>GO Products</title>
    <link
      href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/css/bootstrap.min.css"
      rel="stylesheet"
      integrity="sha384-GLhlTQ8iRABdZLl6O3oVMWSktQOp6b7In1Zl3/Jr59b6EGGoI1aFkw7cmDA6j6gD"
      crossorigin="anonymous"
    />
  </head>
  <body>
    <!-- Navar -->
    <nav class="navbar navbar-expand-lg bg-dark">
      <div class="container">
        <a class="navbar-brand text-light" href="/">Go Products</a>
        <button
          class="navbar-toggler"
          type="button"
          data-bs-toggle="collapse"
          data-bs-target="#navbarNav"
          aria-controls="navbarNav"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav ms-auto">
            <li class="nav-item pe-3">
              <a
                class="nav-link active text-light"
                aria-current="page"
                href="/products"
                >Products</a
              >
            </li>
            <li class="nav-item">
              <a class="nav-link active text-light" href="/categories"
                >Categories</a
              >
            </li>
          </ul>
        </div>
      </div>
    </nav>
    <!-- End of Navbar -->

    <div class="container mt-3">
      <div class="row d-flex justify-content-center">
        <div class="col-4">
          <h2>Add Category</h2>
          <hr />

          <form action="/categories/add" method="POST">
            <div class="mb-3">
              <label class="form-label">Name</label>
              <input
                type="text"
                class="form-control"
                name="name"
                autocomplete="off"
              />
            </div>
            <div class="float-end">
              <a href="/categories" class="btn btn-secondary">Back</a>
              <button type="submit" class="btn btn-primary">Save</button>
            </div>
          </form>
        </div>
      </div>
    </div>
  </body>
</html>
```

## 3.4 Membuat Tampilan HTML Edit Category
Untuk tampilan Edit dari bagian Category kita perlu memodifikasi bagian body dari tampilan home yang ada pada index.html yang ada pada views/home. Setelah diubah kita hanya perlu mengganti nama file index.html menjadi edit.html dan disimpan ke views/category. Berikut langkah – langkahnya:
1. Bukalah file index.html yang tadi kita buat untuk views/home. Lalu kita ubah bagian bodynya dengan menyesuaikan dengan. Sebagai contoh kita buat tabel seperti berikut dengan memanfaatkan js untuk mengubah data yang ada pada database:
```
    <div class="container mt-3">
      <div class="row d-flex justify-content-center">
        <div class="col-4">
          <h2>Edit Category</h2>
          <hr />

          <form action="/categories/edit" method="POST">
            <input type="hidden" name="id" value="{{ .category.Id }}" />
            <div class="mb-3">
              <label class="form-label">Name</label>
              <input
                type="text"
                class="form-control"
                name="name"
                value="{{ .category.Name}}"
                autocomplete="off"
              />
            </div>
            <div class="float-end">
              <a href="/categories" class="btn btn-secondary">Back</a>
              <button type="submit" class="btn btn-primary">Save</button>
            </div>
          </form>
        </div>
      </div>
    </div>
```

Sehingga struktur kodenya jadi seperti berikut :

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>GO Products</title>
    <link
      href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/css/bootstrap.min.css"
      rel="stylesheet"
      integrity="sha384-GLhlTQ8iRABdZLl6O3oVMWSktQOp6b7In1Zl3/Jr59b6EGGoI1aFkw7cmDA6j6gD"
      crossorigin="anonymous"
    />
  </head>
  <body>
    <!-- Navar -->
    <nav class="navbar navbar-expand-lg bg-dark">
      <div class="container">
        <a class="navbar-brand text-light" href="/">Go Products</a>
        <button
          class="navbar-toggler"
          type="button"
          data-bs-toggle="collapse"
          data-bs-target="#navbarNav"
          aria-controls="navbarNav"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav ms-auto">
            <li class="nav-item pe-3">
              <a
                class="nav-link active text-light"
                aria-current="page"
                href="/products"
                >Products</a
              >
            </li>
            <li class="nav-item">
              <a class="nav-link active text-light" href="/categories"
                >Categories</a
              >
            </li>
          </ul>
        </div>
      </div>
    </nav>
    <!-- End of Navbar -->

    <div class="container mt-3">
      <div class="row d-flex justify-content-center">
        <div class="col-4">
          <h2>Edit Category</h2>
          <hr />

          <form action="/categories/edit" method="POST">
            <input type="hidden" name="id" value="{{ .category.Id }}" />
            <div class="mb-3">
              <label class="form-label">Name</label>
              <input
                type="text"
                class="form-control"
                name="name"
                value="{{ .category.Name}}"
                autocomplete="off"
              />
            </div>
            <div class="float-end">
              <a href="/categories" class="btn btn-secondary">Back</a>
              <button type="submit" class="btn btn-primary">Save</button>
            </div>
          </form>
        </div>
      </div>
    </div>
  </body>
</html>
```

## 3.5 Membuat Tampilan HTML Home Product
Untuk tampilan Home dari bagian Product kita perlu memodifikasi bagian body dari tampilan home yang ada pada index.html yang ada pada views/home. Setelah diubah kita hanya perlu memindahkan file index.html untuk bagian category ke views/product. Berikut langkah – langkahnya:
1. Bukalah file index.html yang tadi kita buat untuk views/home. Lalu kita ubah bagian bodynya dengan menyesuaikan dengan kebutuhan. Sebagai contoh kita buat tabel seperti berikut dengan memanfaatkan js untuk membuat baris baru dari setiap baris data yang ada pada database:
```
    <div class="container mt-3">
      <h2>List Products</h2>
      <hr />
      <a href="/products/add" class="btn btn-primary">Add Product</a>
      <table class="table table-bordered mt-2 text-center">
        <thead>
          <tr>
            <th>Name</th>
            <th>Category</th>
            <th>Stock</th>
            <th>Action</th>
          </tr>
        </thead>
        <tbody>
          {{range .products}}
          <tr>
            <td>{{.Name}}</td>
            <td>{{.Category.Name}}</td>
            <td>{{.Stock}}</td>
            <td>
              <a
                href="/products/detail?id={{.Id}}"
                class="btn btn-sm btn-info text-light"
                >Detail</a
              >
              <a
                href="/products/edit?id={{.Id}}"
                class="btn btn-sm btn-warning text-light"
                >Edit</a
              >
              <a
                href="/products/delete?id={{.Id}}"
                onclick="return confirm('Are you sure want to delete this product ?')"
                class="btn btn-sm btn-danger"
                >Delete</a
              >
            </td>
          </tr>
          {{end}}
        </tbody>
      </table>
    </div>
```

Sehingga struktur kodenya jadi seperti berikut:

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>GO Products</title>
    <link
      href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/css/bootstrap.min.css"
      rel="stylesheet"
      integrity="sha384-GLhlTQ8iRABdZLl6O3oVMWSktQOp6b7In1Zl3/Jr59b6EGGoI1aFkw7cmDA6j6gD"
      crossorigin="anonymous"
    />
  </head>
  <body>
    <!-- Navar -->
    <nav class="navbar navbar-expand-lg bg-dark">
      <div class="container">
        <a class="navbar-brand text-light" href="/">Go Products</a>
        <button
          class="navbar-toggler"
          type="button"
          data-bs-toggle="collapse"
          data-bs-target="#navbarNav"
          aria-controls="navbarNav"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav ms-auto">
            <li class="nav-item pe-3">
              <a
                class="nav-link active text-light"
                aria-current="page"
                href="/products"
                >Products</a
              >
            </li>
            <li class="nav-item">
              <a class="nav-link active text-light" href="/categories"
                >Categories</a
              >
            </li>
          </ul>
        </div>
      </div>
    </nav>
    <!-- End of Navbar -->

    <div class="container mt-3">
      <h2>List Products</h2>
      <hr />
      <a href="/products/add" class="btn btn-primary">Add Product</a>
      <table class="table table-bordered mt-2 text-center">
        <thead>
          <tr>
            <th>Name</th>
            <th>Category</th>
            <th>Stock</th>
            <th>Action</th>
          </tr>
        </thead>
        <tbody>
          {{range .products}}
          <tr>
            <td>{{.Name}}</td>
            <td>{{.Category.Name}}</td>
            <td>{{.Stock}}</td>
            <td>
              <a
                href="/products/detail?id={{.Id}}"
                class="btn btn-sm btn-info text-light"
                >Detail</a
              >
              <a
                href="/products/edit?id={{.Id}}"
                class="btn btn-sm btn-warning text-light"
                >Edit</a
              >
              <a
                href="/products/delete?id={{.Id}}"
                onclick="return confirm('Are you sure want to delete this product ?')"
                class="btn btn-sm btn-danger"
                >Delete</a
              >
            </td>
          </tr>
          {{end}}
        </tbody>
      </table>
    </div>
  </body>
</html>
```

## 3.6 Membuat Tampilan HTML Create Product
Untuk tampilan create dari bagian product kita perlu memodifikasi bagian body dari tampilan home yang ada pada index.html yang ada pada views/home. Setelah diubah kita hanya perlu mengganti nama file index.html menjadi create.html dan disimpan ke views/product. Berikut langkah – langkahnya:
1. Bukalah file index.html yang tadi kita buat untuk views/home. Lalu kita ubah bagian bodynya dengan menyesuaikan dengan kebutuhan. Sebagai contoh kita buat tabel seperti berikut dengan memanfaatkan js untuk membuat form input data kategori baru:
```
    <DIV CLASS="CONTAINER MT-3">
      <DIV CLASS="ROW D-FLEX JUSTIFY-CONTENT-CENTER">
        <DIV CLASS="COL-4">
          <H2>ADD PRODUCTS</H2>
          <HR />
          <FORM ACTION="/PRODUCTS/ADD" METHOD="POST">
            <DIV CLASS="MB-3">
              <LABEL CLASS="FORM-LABEL">NAME</LABEL>
              <INPUT
                TYPE="TEXT"
                CLASS="FORM-CONTROL"
                NAME="NAME"
                AUTOCOMPLETE="OFF"
              />
            </DIV>
            <DIV CLASS="MB-3">
              <SELECT CLASS="FORM-SELECT" NAME="CATEGORY_ID">
                {{RANGE .CATEGORIES}}
                <OPTION VALUE="{{ .ID}}">{{.NAME}}</OPTION>
                {{END}}
              </SELECT>
            </DIV>
            <DIV CLASS="MB-3">
              <LABEL CLASS="FORM-LABEL">STOCK</LABEL>
              <INPUT
                TYPE="NUMBER"
                CLASS="FORM-CONTROL"
                NAME="STOCK"
                AUTOCOMPLETE="OFF"
              />
            </DIV>
            <DIV CLASS="MB-3">
              <LABEL CLASS="FORM-LABEL">DESCRIPTION</LABEL>
              <TEXTAREA
                CLASS="FORM-CONTROL"
                NAME="DESCRIPTION"
                ROWS="3"
              ></TEXTAREA>
            </DIV>
            <DIV CLASS="FLOAT-END">
              <A HREF="/PRODUCTS" CLASS="BTN BTN-SECONDARY">BACK</A>
              <BUTTON TYPE="SUBMIT" CLASS="BTN BTN-PRIMARY">SAVE</BUTTON>
            </DIV>
          </FORM>
        </DIV>
      </DIV>
    </DIV>
```

Sehingga struktur kodenya jadi seperti berikut :

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>GO Products</title>
    <link
      href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/css/bootstrap.min.css"
      rel="stylesheet"
      integrity="sha384-GLhlTQ8iRABdZLl6O3oVMWSktQOp6b7In1Zl3/Jr59b6EGGoI1aFkw7cmDA6j6gD"
      crossorigin="anonymous"
    />
  </head>
  <body>
    <!-- Navar -->
    <nav class="navbar navbar-expand-lg bg-dark">
      <div class="container">
        <a class="navbar-brand text-light" href="/">Go Products</a>
        <button
          class="navbar-toggler"
          type="button"
          data-bs-toggle="collapse"
          data-bs-target="#navbarNav"
          aria-controls="navbarNav"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav ms-auto">
            <li class="nav-item pe-3">
              <a
                class="nav-link active text-light"
                aria-current="page"
                href="/products"
                >Products</a
              >
            </li>
            <li class="nav-item">
              <a class="nav-link active text-light" href="/categories"
                >Categories</a
              >
            </li>
          </ul>
        </div>
      </div>
    </nav>
    <!-- End of Navbar -->

    <div class="container mt-3">
      <div class="row d-flex justify-content-center">
        <div class="col-4">
          <h2>Add Products</h2>
          <hr />

          <form action="/products/add" method="POST">
            <div class="mb-3">
              <label class="form-label">Name</label>
              <input
                type="text"
                class="form-control"
                name="name"
                autocomplete="off"
              />
            </div>
            <div class="mb-3">
              <select class="form-select" name="category_id">
                {{range .categories}}
                <option value="{{ .Id}}">{{.Name}}</option>
                {{end}}
              </select>
            </div>
            <div class="mb-3">
              <label class="form-label">Stock</label>
              <input
                type="number"
                class="form-control"
                name="stock"
                autocomplete="off"
              />
            </div>
            <div class="mb-3">
              <label class="form-label">Description</label>
              <textarea
                class="form-control"
                name="description"
                rows="3"
              ></textarea>
            </div>
            <div class="float-end">
              <a href="/products" class="btn btn-secondary">Back</a>
              <button type="submit" class="btn btn-primary">Save</button>
            </div>
          </form>
        </div>
      </div>
    </div>
  </body>
</html>
```

## 3.7 Membuat Tampilan HTML Edit Product
Untuk tampilan edit dari bagian Product kita perlu memodifikasi bagian body dari tampilan home yang ada pada index.html yang ada pada views/home. Setelah diubah kita hanya perlu mengganti nama file index.html menjadi edit.html dan disimpan ke views/product. Berikut langkah – langkahnya:
1. Bukalah file index.html yang tadi kita buat untuk views/home. Lalu kita ubah bagian bodynya dengan menyesuaikan dengan. Sebagai contoh kita buat tabel seperti berikut dengan memanfaatkan js untuk mengubah data yang ada pada database:
```
   <div class="container mt-3">
      <div class="row d-flex justify-content-center">
        <div class="col-4">
          <h2>Edit Products</h2>
          <hr />

          <form action="/products/edit" method="POST">
            <input type="hidden" name="id" value="{{ .product.Id }}" />
            <div class="mb-3">
              <label class="form-label">Name</label>
              <input
                type="text"
                class="form-control"
                name="name"
                value="{{ .product.Name}}"
              />
            </div>
            <div class="mb-3">
              <select class="form-select" name="category_id">
                {{range .categories}}
                <option value="{{ .Id}}">{{ .Name }}</option>
                {{end}}
              </select>
            </div>
            <div class="mb-3">
              <label class="form-label">Stock</label>
              <input
                type="number"
                class="form-control"
                name="stock"
                value="{{ .product.Stock}}"
                autocomplete="off"
              />
            </div>
            <div class="mb-3">
              <label class="form-label">Description</label>
              <textarea class="form-control" name="description" rows="3">
{{ .product.Description}}</textarea
              >
            </div>
            <div class="float-end">
              <a href="/products" class="btn btn-secondary">Back</a>
              <button type="submit" class="btn btn-primary">Save</button>
            </div>
          </form>
        </div>
      </div>
    </div>
```

Sehingga struktur kodenya jadi seperti berikut :

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>GO Products</title>
    <link
      href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/css/bootstrap.min.css"
      rel="stylesheet"
      integrity="sha384-GLhlTQ8iRABdZLl6O3oVMWSktQOp6b7In1Zl3/Jr59b6EGGoI1aFkw7cmDA6j6gD"
      crossorigin="anonymous"
    />
  </head>
  <body>
    <!-- Navar -->
    <nav class="navbar navbar-expand-lg bg-dark">
      <div class="container">
        <a class="navbar-brand text-light" href="/">Go Products</a>
        <button
          class="navbar-toggler"
          type="button"
          data-bs-toggle="collapse"
          data-bs-target="#navbarNav"
          aria-controls="navbarNav"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav ms-auto">
            <li class="nav-item pe-3">
              <a
                class="nav-link active text-light"
                aria-current="page"
                href="/products"
                >Products</a
              >
            </li>
            <li class="nav-item">
              <a class="nav-link active text-light" href="/categories"
                >Categories</a
              >
            </li>
          </ul>
        </div>
      </div>
    </nav>
    <!-- End of Navbar -->

    <div class="container mt-3">
      <div class="row d-flex justify-content-center">
        <div class="col-4">
          <h2>Edit Products</h2>
          <hr />

          <form action="/products/edit" method="POST">
            <input type="hidden" name="id" value="{{ .product.Id }}" />
            <div class="mb-3">
              <label class="form-label">Name</label>
              <input
                type="text"
                class="form-control"
                name="name"
                value="{{ .product.Name}}"
              />
            </div>
            <div class="mb-3">
              <select class="form-select" name="category_id">
                {{range .categories}}
                <option value="{{ .Id}}">{{ .Name }}</option>
                {{end}}
              </select>
            </div>
            <div class="mb-3">
              <label class="form-label">Stock</label>
              <input
                type="number"
                class="form-control"
                name="stock"
                value="{{ .product.Stock}}"
                autocomplete="off"
              />
            </div>
            <div class="mb-3">
              <label class="form-label">Description</label>
              <textarea class="form-control" name="description" rows="3">
{{ .product.Description}}</textarea
              >
            </div>
            <div class="float-end">
              <a href="/products" class="btn btn-secondary">Back</a>
              <button type="submit" class="btn btn-primary">Save</button>
            </div>
          </form>
        </div>
      </div>
    </div>
  </body>
</html>
```

## 3.8 Membuat Tampilan HTML Detail Product
Untuk tampilan Detail dari bagian Product kita perlu memodifikasi bagian body dari tampilan home yang ada pada index.html yang ada pada views/home. Setelah diubah kita hanya perlu mengganti nama file index.html menjadi detao;.html dan disimpan ke views/product. Berikut langkah – langkahnya:
1. Bukalah file index.html yang tadi kita buat untuk views/home. Lalu kita ubah bagian bodynya dengan menyesuaikan dengan. Sebagai contoh kita buat tabel seperti berikut dengan memanfaatkan js untuk menampilkan detail data yang ada pada database:
```
<div class="container mt-3">
      <div class="row d-flex justify-content-center">
        <div class="col-4">
          <h2>Detail Product</h2>
          <hr />

          <form action="/products/add" method="POST">
            <div class="mb-3">
              <label class="form-label">Name</label>
              <input
                type="text"
                class="form-control"
                value="{{ .product.Name}}"
                disabled
              />
            </div>
            <div class="mb-3">
              <label class="form-label">Category</label>
              <input
                type="text"
                class="form-control"
                value="{{ .product.Category.Name}}"
                disabled
              />
            </div>
            <div class="mb-3">
              <label class="form-label">Stock</label>
              <input
                type="number"
                class="form-control"
                name="stock"
                value="{{ .product.Stock}}"
                disabled
              />
            </div>
            <div class="mb-3">
              <label class="form-label">Description</label>
              <textarea
                class="form-control"
                name="description"
                rows="3"
                disabled
              >
{{.product.Description}}</textarea
              >
            </div>
            <div class="float-end">
              <a href="/products" class="btn btn-secondary">Back</a>
            </div>
          </form>
        </div>
      </div>
    </div>
```

Sehingga struktur kodenya jadi seperti berikut :

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>GO Products</title>
    <link
      href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/css/bootstrap.min.css"
      rel="stylesheet"
      integrity="sha384-GLhlTQ8iRABdZLl6O3oVMWSktQOp6b7In1Zl3/Jr59b6EGGoI1aFkw7cmDA6j6gD"
      crossorigin="anonymous"
    />
  </head>
  <body>
    <!-- Navar -->
    <nav class="navbar navbar-expand-lg bg-dark">
      <div class="container">
        <a class="navbar-brand text-light" href="/">Go Products</a>
        <button
          class="navbar-toggler"
          type="button"
          data-bs-toggle="collapse"
          data-bs-target="#navbarNav"
          aria-controls="navbarNav"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav ms-auto">
            <li class="nav-item pe-3">
              <a
                class="nav-link active text-light"
                aria-current="page"
                href="/products"
                >Products</a
              >
            </li>
            <li class="nav-item">
              <a class="nav-link active text-light" href="/categories"
                >Categories</a
              >
            </li>
          </ul>
        </div>
      </div>
    </nav>
    <!-- End of Navbar -->

    <div class="container mt-3">
      <div class="row d-flex justify-content-center">
        <div class="col-4">
          <h2>Detail Product</h2>
          <hr />

          <form action="/products/add" method="POST">
            <div class="mb-3">
              <label class="form-label">Name</label>
              <input
                type="text"
                class="form-control"
                value="{{ .product.Name}}"
                disabled
              />
            </div>
            <div class="mb-3">
              <label class="form-label">Category</label>
              <input
                type="text"
                class="form-control"
                value="{{ .product.Category.Name}}"
                disabled
              />
            </div>
            <div class="mb-3">
              <label class="form-label">Stock</label>
              <input
                type="number"
                class="form-control"
                name="stock"
                value="{{ .product.Stock}}"
                disabled
              />
            </div>
            <div class="mb-3">
              <label class="form-label">Description</label>
              <textarea
                class="form-control"
                name="description"
                rows="3"
                disabled
              >
{{.product.Description}}</textarea
              >
            </div>
            <div class="float-end">
              <a href="/products" class="btn btn-secondary">Back</a>
            </div>
          </form>
        </div>
      </div>
    </div>
  </body>
</html>
```
