# 🧠 Simple Quiz App

A simple and interactive **Quiz Application** built using **HTML, CSS, and JavaScript**.

The application presents multiple-choice questions to the user, allows them to select an answer, provides immediate visual feedback, keeps track of their score, and displays the final result at the end of the quiz.

## 📌 Project Overview

This project was created to practice fundamental **JavaScript programming and DOM manipulation** concepts by building an interactive quiz application.

The quiz currently contains **4 general-knowledge questions**, with **4 answer choices for each question**.

The application allows users to:

* 🧠 Answer multiple-choice questions
* ✅ Identify correct answers
* ❌ Identify incorrect answers
* 📊 Track their score
* ➡️ Move to the next question
* 🔄 Play the quiz again after completion

## ✨ Features

### 🧠 Multiple-Choice Questions

Each question contains four possible answers. The questions and answers are stored in a JavaScript array, making the quiz content easy to modify and extend.

### ✅ Correct Answer Feedback

When the user selects the correct answer:

* The selected option is highlighted as correct.
* The score is increased by 1.

### ❌ Incorrect Answer Feedback

When the user selects an incorrect answer:

* The selected option is highlighted as incorrect.
* The correct answer is also revealed.

The application then disables all answer buttons so the user cannot select multiple answers for the same question.

### 📊 Score Tracking

The application maintains a score throughout the quiz.

After all questions have been answered, the final score is displayed:

```text
You scored X out of 4!
```

The score is calculated using the number of questions in the quiz, so it automatically adapts if more questions are added.

### 🔄 Play Again

After completing the quiz, the **Next** button changes to **Play Again**.

Clicking it resets the question index and score and starts the quiz from the beginning.

## 🛠️ Technologies Used

| Technology           | Purpose                                               |
| -------------------- | ----------------------------------------------------- |
| **HTML5**            | Creates the structure of the quiz                     |
| **CSS3**             | Handles styling, layout, and answer feedback          |
| **JavaScript**       | Controls quiz logic and user interaction              |
| **DOM Manipulation** | Dynamically creates and updates questions and answers |

## 📂 Project Structure

```text
Simple-Quiz/
│
├── index.html
├── style.css
├── script.js
│
└── README.md
```

## 🎨 User Interface

The application has a simple and clean quiz interface.

It consists of:

* Quiz title
* Question display area
* Four answer buttons
* Next button
* Correct-answer feedback
* Incorrect-answer feedback
* Final score display

The HTML structure provides a dedicated question area, an answer-button container, and a Next button.

The CSS uses a dark blue page background with a white quiz card and styled answer buttons. Correct answers are displayed with a green background, while incorrect answers use a red background.

## ⚙️ How It Works

### 1. Store Questions

Questions are stored inside a JavaScript array.

Each question contains:

* The question text
* Four answer options
* A `correct` property identifying the correct option

For example:

```javascript
{
    question: "Which is largest animal in the world?",
    answers: [
        {text: "Shark", correct: false},
        {text: "Blue Whale", correct: true},
        {text: "Elephant", correct: false},
        {text: "Giraffe", correct: false}
    ]
}
```

### 2. Start the Quiz

The `startQuiz()` function initializes the quiz.

It resets:

* Current question index
* Score
* Next button text

Then it displays the first question.

### 3. Display Questions

The `showQuestion()` function retrieves the current question and dynamically creates buttons for each answer.

```javascript
currentQuestion.answers.forEach(answer => {
    const button = document.createElement("button");
    button.innerHTML = answer.text;
    button.classList.add("btn");
    answerButtons.appendChild(button);
});
```

### 4. Select an Answer

When the user clicks an answer, the `selectAnswer()` function determines whether the selected answer is correct.

```javascript
const isCorrect = selectedBtn.dataset.correct === "true";
```

If the answer is correct, the score increases and the button receives the `correct` class.

If it is incorrect, the button receives the `incorrect` class and the correct answer is highlighted.

### 5. Move to the Next Question

The **Next** button increases the current question index.

If more questions remain, the next question is displayed. Otherwise, the final score is shown.

### 6. Display Final Score

Once all questions are completed, the `showScore()` function displays the user's result.

```javascript
questionElement.innerHTML =
    `You scored ${score} out of ${questions.length}!`;
```

The button then changes to **Play Again**.

## 🚀 How to Run the Project

### Step 1: Clone the Repository

```bash
git clone https://github.com/your-username/simple-quiz.git
```

### Step 2: Navigate to the Project

```bash
cd simple-quiz
```

### Step 3: Run the Application

Open `index.html` in your web browser.

You can also use **Live Server** in VS Code for development.

## 🖥️ How to Use

1. Open the application.
2. Read the displayed question.
3. Choose one of the four available answers.
4. View the correct/incorrect feedback.
5. Click **Next** to continue.
6. Complete all questions.
7. View your final score.
8. Click **Play Again** to restart the quiz.

## 📚 Concepts Learned

This project helped practice several important JavaScript and frontend concepts:

* JavaScript arrays
* JavaScript objects
* Functions
* Variables and state management
* `forEach()`
* DOM manipulation
* `createElement()`
* `appendChild()`
* `classList`
* `dataset`
* Event listeners
* Conditional statements
* Dynamic content generation
* Button disabling
* Score calculation

## 🔮 Future Improvements

The application can be extended with additional features such as:

* 📚 More quiz categories
* 🎯 Difficulty levels
* ⏱️ Countdown timer
* 🏆 High-score system
* 📊 Detailed results page
* 🔀 Randomized questions
* 🔀 Randomized answer options
* 📈 Progress indicator
* 💾 Save high scores using Local Storage
* 🎨 Dark/Light mode
* 📱 Improved mobile responsiveness

## 👨‍💻 Author

**Mahendra Patibandla**

Built using **HTML, CSS, and JavaScript** as a frontend development project.

---

⭐ If you found this project useful, consider giving the repository a star!
