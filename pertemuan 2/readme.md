Berikut **penjelasan lengkap per fungsi** dari kode Linked List kamu, dengan bahasa yang mudah dipahami 👇

---

# 📌 **Penjelasan Per Fungsi dalam Program Linked List**

## **1. class Node**

```python
class Node:
    def __init__(self, data=None, pointer=None):
        self.data = data
        self.next = pointer
```

**Fungsi:**

* Membuat struktur node (simpul) pada linked list.
* Setiap node menyimpan:

  * `data` → nilai yang disimpan.
  * `next` → pointer ke node berikutnya.

---

## **2. class Linkedlist**

```python
class Linkedlist:
   def __init__(self):
        self.head = None
```

**Fungsi:**

* Membuat objek Linked List baru.
* `self.head` digunakan sebagai **kepala linked list**, awalnya `None` (kosong).

---

## **3. insert_at_first(self, data)**

```python
def insert_at_first(self, data):
    node = Node(data, self.head)
    self.head = node
```

**Fungsi:**

* Menambahkan data ke **bagian paling depan** (head) dari linked list.
* Node baru akan menunjuk ke head lama, lalu head dipindah ke node baru.

**Contoh:**
Sebelum: `A -> B -> C`
Setelah `insert_at_first("X")`:
→ `X -> A -> B -> C`

---

## **4. insert_at_last(self, data)**

```python
def insert_at_last(self, data):
    if self.head is None:
        self.head = Node(data)
    else:
        node_sekarang = self.head
        while node_sekarang.next:
            node_sekarang = node_sekarang.next
        node = Node(data)
        node_sekarang.next = node
```

**Fungsi:**

* Menambahkan data pada **bagian paling akhir** dari linked list.

**Cara kerja:**

1. Jika list masih kosong → langsung jadikan head.
2. Jika tidak kosong → program berjalan dari head sampai menemukan node terakhir (yang `next`-nya `None`).
3. Node baru ditempel di bagian akhir.

---

## **5. insert_at(self, index, data)**

```python
def insert_at(self, index, data):
    if index < 0 or index > self.length() - 1:
        print("index tidak valid")
    elif index == 0:
        self.insert_at_first(data)
    else:
        urutan = 0
        node_sekarang = self.head
        while urutan < index - 1:
            urutan += 1
            node_sekarang = node_sekarang.next 
        node = Node(data, node_sekarang.next)
        node_sekarang.next = node
```

**Fungsi:**

* Menyisipkan node pada **posisi tertentu** berdasarkan index.

**Cara kerja:**

1. Cek apakah index valid.
2. Jika index 0 → gunakan fungsi **insert_at_first**.
3. Kalau index di tengah → cari node sebelum index tersebut.
4. Sisipkan node baru di posisi itu.

---

## **6. print(self)**

```python
def print(self):
    if self.head is None:
        print("data kosong")
    else:
        text_print = ''
        node_sekarang = self.head
        while node_sekarang:
            text_print += str(node_sekarang.data) + "->"
            node_sekarang = node_sekarang.next
        print(text_print)
```

**Fungsi:**

* Menampilkan seluruh isi linked list dari depan sampai akhir.

**Output Contoh:**
`manggis->mangga->anggur->jeruk->apel->`

---

## **7. length(self)**

```python
def length(self):
      urutan = 0
      data_sekarang = self.head
      while data_sekarang:
         data_sekarang = data_sekarang.next
         urutan += 1
      return urutan
```

**Fungsi:**

* Menghitung jumlah node dalam linked list.
* Mengiterasi node dari head sampai terakhir.

---

## **8. Bagian main program**

```python
LL = Linkedlist()

LL.insert_at_first("jeruk")
LL.insert_at_first("mangga")
LL.insert_at_first("manggis")
LL.insert_at_last("apel")
LL.insert_at(2, "anggur")

LL.print()
print(LL.length())
```

**Fungsi:**

* Membuat linked list dan mengisi datanya.
* Menampilkan hasil dan panjang linked list.

**Output final:**

```
manggis->mangga->anggur->jeruk->apel->
5
```

---

Kalau mau, aku bisa buatkan **diagram alur**, **gambar node**, atau **versi kode yang diperbaiki**. Mau?
