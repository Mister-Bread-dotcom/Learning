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
      appBar: AppBar(title: Text("Math Learning App")),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: <Widget>[
            ElevatedButton(
              onPressed: () {
                Navigator.push(context, MaterialPageRoute(builder: (context) => LessonPage()));
              },
              child: Text('ابدأ التعلم'),
            ),
          ],
        ),
      ),
    );
  }
}

class LessonPage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text("التمارين الحسابية")),
      body: Padding(
        padding: const EdgeInsets.all(16.0),
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.start,
          children: [
            QuizCard(
              question: "ما هو ناتج 3 + 4؟",
              correctAnswer: "7",
              wrongAnswerFeedback: "الإجابة خاطئة! حاول مرة أخرى.",
            ),
            QuizCard(
              question: "ما هو ناتج 8 - 2؟",
              correctAnswer: "6",
              wrongAnswerFeedback: "الإجابة خاطئة! حاول مرة أخرى.",
            ),
            QuizCard(
              question: "ما هو ناتج 5 * 3؟",
              correctAnswer: "15",
              wrongAnswerFeedback: "الإجابة خاطئة! حاول مرة أخرى.",
            ),
            QuizCard(
              question: "ما هو ناتج 9 ÷ 3؟",
              correctAnswer: "3",
              wrongAnswerFeedback: "الإجابة خاطئة! حاول مرة أخرى.",
            ),
          ],
        ),
      ),
    );
  }
}

class QuizCard extends StatefulWidget {
  final String question;
  final String correctAnswer;
  final String wrongAnswerFeedback;

  QuizCard({required this.question, required this.correctAnswer, required this.wrongAnswerFeedback});

  @override
  _QuizCardState createState() => _QuizCardState();
}

class _QuizCardState extends State<QuizCard> {
  final TextEditingController _controller1 = TextEditingController();
  final TextEditingController _controller2 = TextEditingController();
  String _feedback = '';

  void _checkAnswer() {
    if (_controller1.text == widget.correctAnswer && _controller2.text == widget.correctAnswer) {
      setState(() {
        _feedback = 'إجابة صحيحة!';
      });
    } else {
      setState(() {
        _feedback = widget.wrongAnswerFeedback;
      });
    }
  }

  @override
  Widget build(BuildContext context) {
    return Card(
      margin: EdgeInsets.symmetric(vertical: 10),
      child: Padding(
        padding: const EdgeInsets.all(16.0),
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.start,
          children: [
            Text(widget.question, style: TextStyle(fontSize: 18)),
            SizedBox(height: 10),
            Row(
              children: [
                Expanded(
                  child: TextField(
                    controller: _controller1,
                    keyboardType: TextInputType.number,
                    decoration: InputDecoration(hintText: "أدخل الإجابة الأولى"),
                  ),
                ),
                SizedBox(width: 10),
                Expanded(
                  child: TextField(
                    controller: _controller2,
                    keyboardType: TextInputType.number,
                    decoration: InputDecoration(hintText: "أدخل الإجابة الثانية"),
                  ),
                ),
              ],
            ),
            SizedBox(height: 10),
            ElevatedButton(
              onPressed: _checkAnswer,
              child: Text("تحقق الإجابة"),
            ),
            Text(_feedback, style: TextStyle(fontSize: 16, fontWeight: FontWeight.bold)),
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
        primarySwatch: Colors.green,
      ),
      home: HomePage(),
    );
  }
}

class HomePage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text("Apprendre les mathématiques")),
      body: Padding(
        padding: const EdgeInsets.all(16.0),
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: <Widget>[
            Text("Voici l'histoire :"),
            Text(
              "Ahmed a 10 pommes et il en donne 3 à son ami. Combien de pommes lui restent-ils ?",
              style: TextStyle(fontSize: 18),
            ),
            SizedBox(height: 20),
            QuizCard(
              question: "Combien de pommes Ahmed a-t-il maintenant?",
              correctAnswer: "7",
              wrongAnswerFeedback: "Non, essayez encore. Il a donné 3 pommes.",
            ),
            SizedBox(height: 20),
            Text(
              "Si Ahmed avait 20 pommes et il en partageait également avec 4 amis, combien chaque ami recevrait-il ?",
              style: TextStyle(fontSize: 18),
            ),
            SizedBox(height: 20),
            QuizCard(
              question: "Combien chaque ami recevra-t-il ?",
              correctAnswer: "5",
              wrongAnswerFeedback: "Non, essayez encore. Il a partagé les pommes entre 4 amis.",
            ),
          ],
        ),
      ),
    );
  }
}

class QuizCard extends StatefulWidget {
  final String question;
  final String correctAnswer;
  final String wrongAnswerFeedback;

  QuizCard({required this.question, required this.correctAnswer, required this.wrongAnswerFeedback});

  @override
  _QuizCardState createState() => _QuizCardState();
}

class _QuizCardState extends State<QuizCard> {
  final TextEditingController _controller = TextEditingController();
  String _feedback = '';

  void _checkAnswer() {
    if (_controller.text == widget.correctAnswer) {
      setState(() {
        _feedback = 'Réponse correcte!';
      });
    } else {
      setState(() {
        _feedback = widget.wrongAnswerFeedback;
      });
    }
  }

  @override
  Widget build(BuildContext context) {
    return Card(
      margin: EdgeInsets.symmetric(vertical: 10),
      child: Padding(
        padding: const EdgeInsets.all(16.0),
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.start,
          children: [
            Text(widget.question, style: TextStyle(fontSize: 18)),
            SizedBox(height: 10),
            TextField(
              controller: _controller,
              keyboardType: TextInputType.number,
              decoration: InputDecoration(hintText: "Entrez votre réponse ici"),
            ),
            SizedBox(height: 10),
            ElevatedButton(
              onPressed: _checkAnswer,
              child: Text("Vérifier la réponse"),
            ),
            Text(_feedback, style: TextStyle(fontSize: 16, fontWeight: FontWeight.bold)),
          ],
        ),
      ),
    );
  }
}