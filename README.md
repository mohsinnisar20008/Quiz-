# Simple Python Quiz Game

def ask_question(question, options, correct_option):
    print(question)
    for idx, option in enumerate(options, 1):
        print(f"{idx}. {option}")
    
    while True:
        try:
            answer = int(input("Please select the correct answer (1-4): "))
            if 1 <= answer <= 4:
                break
            else:
                print("Please select a valid option (1-4).")
        except ValueError:
            print("Invalid input! Please enter a number between 1 and 4.")
    
    if options[answer - 1] == correct_option:
        return True
    else:
        return False

def main():
    print("Welcome to the Python Quiz Game!")
    
    score = 0
    total_questions = 3
    
    # Questions: Each question is a tuple of (question, list_of_options, correct_option)
    questions = [
        ("What is the capital of France?", ["Berlin", "Madrid", "Paris", "Rome"], "Paris"),
        ("Which one of these is a Python data type?", ["int", "integer", "number", "floaty"], "int"),
        ("Who developed Python?", ["Guido van Rossum", "Elon Musk", "Bill Gates", "Mark Zuckerberg"], "Guido van Rossum")
    ]
    
    # Ask each question
    for question, options, correct_option in questions:
        if ask_question(question, options, correct_option):
            print("Correct!\n")
            score += 1
        else:
            print(f"Wrong! The correct answer was: {correct_option}\n")
    
    # Game over, display the score
    print(f"Game Over! You scored {score} out of {total_questions}.")

if __name__ == "__main__":
    main()
