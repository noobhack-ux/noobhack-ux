class Question:
    def __init__(self, question, options, correct_option):
        self.question = question
        self.options = options
        self.correct_option = correct_option

class Quiz:
    def __init__(self):
        self.questions = []
        self.score = 0

    def add_question(self, question):
        self.questions.append(question)

    def start_quiz(self):
        for idx, question in enumerate(self.questions, start=1):
            print(f"Question {idx}: {question.question}")
            for option_idx, option in enumerate(question.options, start=1):
                print(f"{option_idx}. {option}")
            
            user_choice = int(input("Your choice: "))
            if user_choice == question.correct_option:
                print("Correct!\n")
                self.score += 1
            else:
                print(f"Wrong! Correct answer: {question.correct_option}\n")
        
        print(f"Quiz completed. Your score: {self.score}/{len(self.questions)}")

# Sample questions
q1 = Question("What is the capital of Bangladesh?",
              ["Dhaka", "Chittagong", "Rajshahi", "Khulna"],
              correct_option=1)

q2 = Question("Which planet is known as the 'Red Planet'?",
              ["Mars", "Venus", "Jupiter", "Saturn"],
              correct_option=1)

# Create a quiz
quiz = Quiz()
quiz.add_question(q1)
quiz.add_question(q2)

# Start the quiz
quiz.start_quiz()
