 الحسابية # Learning
تعلم رياضيات
git clone https://github.com/USERNAME/MyMathApp.git
git commit -m "أضفت ملف جديد لشرح العمليات الحسابية"
أضفت ملف جديد لشرح العمليات الحسابية
git push origin main
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Math Learning App',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: HomePage(),
    );
  }
}

class HomePage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text("Math Learning App"),
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: <Widget>[
            ElevatedButton(
              onPressed: () {
                // انتقل إلى صفحة الابتدائي
              },
              child: Text('ابتدائي'),
            ),
            ElevatedButton(
              onPressed: () {
                // انتقل إلى صفحة الإعدادي
              },
              child: Text('إعدادي'),
            ),
          ],
        ),
      ),
    );
  }
}
class LessonPage extends StatelessWidget {
  final String title;
  final String content;
  final String example;

  LessonPage({required this.title, required this.content, required this.example});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text(title)),
      body: Padding(
        padding: const EdgeInsets.all(16.0),
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.start,
          children: [
            Text(content, style: TextStyle(fontSize: 18)),
            SizedBox(height: 20),
            Text("مثال: $example", style: TextStyle(fontSize: 16, fontWeight: FontWeight.bold)),
          ],
        ),
      ),
    );
  }
}
class QuizPage extends StatefulWidget {
  @override
  _QuizPageState createState() => _QuizPageState();
}

class _QuizPageState extends State<QuizPage> {
  final TextEditingController _controller = TextEditingController();
  String _feedback = '';

  void _checkAnswer() {
    if (_controller.text == '5') {
      setState(() {
        _feedback = 'إجابة صحيحة!';
      });
    } else {
      setState(() {
        _feedback = 'إجابة خاطئة. حاول مرة أخرى.';
      });
    }
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text("تمرين")),
      body: Padding(
        padding: const EdgeInsets.all(16.0),
        child: Column(
          children: [
            Text("ما هو ناتج 2 + 3؟"),
            TextField(
              controller: _controller,
              keyboardType: TextInputType.number,
              decoration: InputDecoration(hintText: "أدخل الإجابة هنا"),
            ),
            ElevatedButton(
              onPressed: _checkAnswer,
              child: Text("تحقق الإجابة"),
            ),
            Text(_feedback, style: TextStyle(fontSize: 18, fontWeight: FontWeight.bold)),
          ],
        ),
      ),
    );
  }
}
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Math Learning App',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: HomePage(),
    );
  }
}

class HomePage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text("Math Learning App"),
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: <Widget>[
            ElevatedButton(
              onPressed: () {
                Navigator.push(context, MaterialPageRoute(builder: (context) => LessonPage(title: "العمليات الحسابية", content: "في هذا الدرس سنتعلم العمليات الحسابية: الجمع، الطرح، الضرب والقسمة.", example: "مثال: 2 + 3 = 5")));
              },
              child: Text('ابتدائي'),
            ),
            ElevatedButton(
              onPressed: () {
                Navigator.push(context, MaterialPageRoute(builder: (context) => LessonPage(title: "العمليات الحسابية المتقدمة", content: "في هذا الدرس سنتعلم العمليات الحسابية المتقدمة.", example: "مثال: 5 * 6 = 30")));
              },
              child: Text('إعدادي'),
            ),
          ],
        ),
      ),
    );
  }
}

class LessonPage extends StatelessWidget {
  final String title;
  final String content;
  final String example;

  LessonPage({required this.title, required this.content, required this.example});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text(title)),
      body: Padding(
        padding: const EdgeInsets.all(16.0),
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.start,
          children: [
            Text(content, style: TextStyle(fontSize: 18)),
            SizedBox(height: 20),
            Text("مثال: $example", style: TextStyle(fontSize: 16, fontWeight: FontWeight.bold)),
            SizedBox(height: 20),
            ElevatedButton(
              onPressed: () {
                Navigator.push(context, MaterialPageRoute(builder: (context) => QuizPage()));
              },
              child: Text('انتقل إلى التمرين'),
            ),
          ],
        ),
      ),
    );
  }
}

class QuizPage extends StatefulWidget {
  @override
  _QuizPageState createState() => _QuizPageState();
}

class _QuizPageState extends State<QuizPage> {
  final TextEditingController _controller = TextEditingController();
  String _feedback = '';

  void _checkAnswer() {
    if (_controller.text == '5') {
      setState(() {
        _feedback = 'إجابة صحيحة!';
      });
    } else {
      setState(() {
        _feedback = 'إجابة خاطئة. حاول مرة أخرى.';
      });
    }
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text("تمرين")),
      body: Padding(
        padding: const EdgeInsets.all(16.0),
        child: Column(
          children: [
            Text("ما هو ناتج 2 + 3؟"),
            TextField(
              controller: _controller,
              keyboardType: TextInputType.number,
              decoration: InputDecoration(hintText: "أدخل الإجابة هنا"),
            ),
            ElevatedButton(
              onPressed: _checkAnswer,
              child: Text("تحقق الإجابة"),
            ),
            Text(_feedback, style: TextStyle(fontSize: 18, fontWeight: FontWeight.bold)),
          ],
        ),
      ),
    );
  }
}