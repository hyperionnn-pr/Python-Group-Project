# Simple Grade Analyzer

subjects = []
grades = []

print("Enter your subjects and grades (type 'done' to stop):")

while True:
    subject = input("Subject: ")
    
    if subject.lower() == "done":
        break
        
    try:
        grade = float(input("Grade: "))
        subjects.append(subject)
        grades.append(grade)
    except ValueError:
        print("Please enter a valid number for the grade.")

if len(grades) > 0:
    # Compute average
    average = sum(grades) / len(grades)

    # Find weakest subject 
    lowest_grade = max(grades)
    index = grades.index(lowest_grade)
    weak_subject = subjects[index]

    # Output
    print("\n--- RESULTS ---")
    print(f"Average: {round(average, 2)}")
    print(f"Focus on: {weak_subject} (Grade: {lowest_grade})")

    # Simple advice 
    if average <= 1.5:
        print("Excellent!")
    elif average <= 2.0:
        print("Good, but improve your weak subject.")
    else:
        print("You need to study more.")
else:
    print("No data entered. Invalid Output")
