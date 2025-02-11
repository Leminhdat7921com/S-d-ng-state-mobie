# S-d-ng-state-mobie
lê minh đạt - 19810310083 

import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return const MaterialApp(
      debugShowCheckedModeBanner: false,
      home: ColorChangerScreen(),
    );
  }
}

class ColorChangerScreen extends StatefulWidget {
  const ColorChangerScreen({super.key});

  @override
  _ColorChangerScreenState createState() => _ColorChangerScreenState();
}

class _ColorChangerScreenState extends State<ColorChangerScreen> {
  Color _backgroundColor = Colors.green; // Màu nền mặc định
  String _colorName = "GREEN"; // Tên màu mặc định

  void _changeColor(Color color, String name) {
    setState(() {
      _backgroundColor = color;
      _colorName = name;
    });
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: _backgroundColor,
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            Text(
              _colorName, // Hiển thị tên màu tương ứng
              style: const TextStyle(fontSize: 24, color: Colors.white),
            ),
            const SizedBox(height: 20),
            _buildColorButton('BLUE', Colors.blue),
            _buildColorButton('BROWN', Colors.brown),
            _buildColorButton('YELLOW', Colors.yellow, textColor: Colors.black),
            _buildColorButton('RED', Colors.red),
            _buildColorButton('BLACK', Colors.black),
          ],
        ),
      ),
    );
  }

  Widget _buildColorButton(String text, Color color, {Color textColor = Colors.white}) {
    return Padding(
      padding: const EdgeInsets.symmetric(vertical: 5),
      child: ElevatedButton(
        onPressed: () => _changeColor(color, text), // Đổi màu và cập nhật tên màu
        style: ElevatedButton.styleFrom(
          backgroundColor: color,
          minimumSize: const Size(200, 50),
        ),
        child: Text(text, style: TextStyle(fontSize: 20, color: textColor)),
      ),
    );
  }
}


![image](https://github.com/user-attachments/assets/6c0d5445-613d-49ec-89a2-7ef782794e9f)


