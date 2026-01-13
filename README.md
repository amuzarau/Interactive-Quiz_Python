# 🧠 Interactive Quiz  
**Python • Object-Oriented Design • XML Data Storage**

An interactive **terminal-based quiz application** built with Python using **Object-Oriented Programming (OOP)** and **XML-driven data**.  
The system allows users to take quizzes, track their results, and save outcomes in .txt format — while allowing new quizzes to be added **without changing the code**.

This project is based on the Joe Marini LinkedIn Learning course and extended as an educational OOP + data-driven architecture example.

---

# 🚀 Key Features

- 📚 List all available quizzes  
- 📝 Take quizzes with **Multiple-Choice** and **True/False** questions  
- 📊 Automatically calculate score and statistics  
- 💾 Save quiz results to a `.txt` file  
- 📦 Add new quizzes simply by editing XML files  
- 🧩 Fully object-oriented architecture  

---

# 🧠 Project Advantages

This project demonstrates **real-world backend architecture** principles:

| Concept | How It Is Used |
|--------|----------------|
| **OOP (Object-Oriented Programming)** | Quiz logic, parsing, and UI control are encapsulated in classes |
| **XML as Data Layer** | Questions are stored externally and parsed at runtime |
| **Separation of Concerns** | UI, quiz logic, and data parsing are fully separated |
| **Extensibility** | New quizzes can be added without touching Python code |
| **Testable Architecture** | Classes are isolated and reusable |

This is exactly how professional applications separate **data**, **logic**, and **presentation**.

---

# 🧩 Application Architecture

```mermaid
flowchart TD
    A[User runs pyquiz.py] --> B[QuizApp]
    B --> C[QuizManager]
    C --> D[QuizParser]
    D --> E[XML Quiz Files]
    E --> D
    D --> F[Quiz Objects]
    F --> C
    C --> G[Run Quiz]
    G --> H[User Answers]
    H --> I[Score & Results]
    I --> J[Save to TXT File]
```
---

# 🧱 Class Responsibilities
classDiagram
    class QuizApp {
        +start()
        +show_menu()
        +handle_user_input()
    }

    class QuizManager {
        +list_quizzes()
        +load_quiz()
        +run_quiz()
    }

    class QuizParser {
        +parse_xml()
        +build_quiz()
    }

    class Quiz {
        +questions
        +ask_questions()
        +check_answers()
        +get_score()
    }

    QuizApp --> QuizManager
    QuizManager --> QuizParser
    QuizParser --> Quiz
    
---

# 📁 File & Class Responsibilities
File / Class	Role
pyquiz.py	Application entry point. Starts the program and displays the menu
QuizApp	Controls the user experience (menu, navigation, exit)
QuizManager	Manages available quizzes and user actions
QuizParser	Reads XML files and builds Quiz objects
Quiz	Contains questions, handles user answers, calculates score
*.xml	Stores all quiz data (questions, options, correct answers)
*.txt	Stores saved quiz results

---

🧠 How XML Powers the App

Instead of hard-coding questions, quizzes are stored like this:

<quiz>
  <question>
    <type>multiple</type>
    <text>What does OOP stand for?</text>
    <choice>A) Only One Program</choice>
    <choice>B) Object Oriented Programming</choice>
    <choice>C) Open Office Protocol</choice>
    <answer>B</answer>
  </question>
</quiz>


This allows:
- Teachers to create quizzes
- No code changes
- Easy versioning and scaling
- Data reuse in GUI or web versions later

---

# 🖥️ Running the App

Right-click pyquiz.py

Run in terminal

Enter your name

Use the menu:

(M) Repeat menu
(L) List quizzes
(T) Take a quiz
(E) Exit


After finishing a quiz, you will see:

Date & time
Number of questions
Correct answers
Total score
You can then save it as a .txt file.

---

# 📈 Future Upgrades

- Web or GUI interface (FastAPI / Tkinter)
- Question categories
- User profiles
- Leaderboards
- JSON support
