# Chapter 12: Meningkatkan Context API

## GitHube Pages
Link: [Theme Switcher](https://fatahpratam.github.io/tutorial-theme-switcher/)

## Youtube Tutorial
- Link: [Full Stack React Developer Course with Appwrite](https://www.youtube.com/watch?v=Bvwq_S0n2pk)
- Creator: [HiteshCodeLab](https://www.youtube.com/@HiteshCodeLab)

## Gambaran umum
- Walaupun kode untuk membuat dan menggunakan `Context` sebelumnya berhasil, terdapat pengulangan pemanggilan `UserContext` ketika memanggil `useContext()` yang dapat dihindari.

## Cara mengatur Context API lebih baik
### Membuat `Context`
- Buat file User.js untuk membuat `Context` sekaligus `UserContextProvider`.
- Panggil method `createContext()` akan tetapi, kali ini beri argument object dengan  property `user` dan `setUser`. Ini sekedar dilakukan untuk pendeklarasian property-property apa saja yang akan digunakan di dalam provider.
- Simpan hasil fungsi sebelumnya ke dalam variabel (mis: `UserContext`) dan export variabel tersebut.
- Buat alias dari `UserContext.Provider` sebagai variabel `UserProvider` dan export variabel tersebut. Ini dilakukan untuk mempersingkat pemanggilan context provider.
- Buat fungsi `useUser()` yang akan mengembalikan `useContext(UserContext)` dan export fungsi tersebut. Ini dilakukan untuk menghindari pengulangan pemanggilan `UserContext`.

### Menggunakan `Context`
- Buat state untuk variabel `user` dengan `setUser` sebagai fungsi pengubah state.
- Selanjutnya, import `UserContext` dan apit component yang akan menggunakan `Context` dengan JSX `UserContext`. Beri juga argument untuk kunci `value` dengan object `{user, setUser}` dari state sebelumya.
- Kini semua component di dalam `UserContext` sudah bisa menggunakan `Context` tersebut.
- Untuk mengakses atau mengubah `Context`, cukup dengan memanggil method `useUser()`.