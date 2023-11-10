import 'dart:async';

import 'package:flutter/material.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'My App',
      home: SplashScreen(), // Gunakan SplashScreen sebagai widget pertama yang ditampilkan
    );
  }
}

class SplashScreen extends StatefulWidget {
  @override
  _SplashScreenState createState() => _SplashScreenState();
}

class _SplashScreenState extends State<SplashScreen> {
  @override
  void initState() {
    super.initState();
    _loadSplashScreen(); // Fungsi untuk menunggu beberapa detik sebelum pindah ke halaman berikutnya
  }

  _loadSplashScreen() async {
    // Tunggu selama 2 detik, gantilah sesuai kebutuhan
    await Future.delayed(Duration(seconds: 2));
    // Pindah ke halaman berikutnya
    Navigator.pushReplacement(
      context,
      MaterialPageRoute(builder: (context) => HomeScreen()), // Ganti HomeScreen dengan halaman berikutnya
    );
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      body: Center(
        child: Image.asset('assets/splash.png'), // Ganti dengan nama file gambar splash screen Anda
      ),
    );
  }
}

class HomeScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Home Screen'),
      ),
      body: Center(
        child: Text('Selamat datang di aplikasi Flutter Anda!'),
      ),
    );
  }
}
