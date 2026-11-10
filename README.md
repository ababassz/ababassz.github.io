
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>BB's Preferences 💜</title>

  <style>
    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      padding: 25px 15px;
      font-family: "Segoe UI", Arial, sans-serif;
      background: linear-gradient(135deg, #f5eaff, #e8d5ff, #fce4f3);
      color: #49345e;
    }

    .container {
      max-width: 750px;
      margin: auto;
    }

    header {
      text-align: center;
      padding: 30px 15px;
    }

    header h1 {
      color: #8b4db5;
      font-size: 2.2rem;
      margin-bottom: 10px;
    }

    header p {
      color: #80658f;
      font-size: 1rem;
    }

    .decoration {
      font-size: 1.8rem;
      margin-bottom: 10px;
    }

    .question-card {
      background: rgba(255, 255, 255, 0.85);
      border: 2px solid #ead7fa;
      border-radius: 18px;
      padding: 23px;
      margin-bottom: 20px;
      box-shadow: 0 5px 15px rgba(128, 75, 160, 0.08);
    }

    .question-card h2 {
      color: #8b4db5;
      font-size: 1.15rem;
      margin-top: 0;
      margin-bottom: 18px;
    }

    .option {
      display: flex;
      align-items: center;
      gap: 10px;
      background: #faf5ff;
      border: 1px solid #eadcf7;
      border-radius: 12px;
      padding: 12px;
      margin: 9px 0;
      cursor: pointer;
      transition: 0.2s;
    }

    .option:hover {
      background: #f0e2ff;
      border-color: #bd91df;
    }

    .option input {
      accent-color: #9b59c6;
      width: 17px;
      height: 17px;
      cursor: pointer;
    }

    .option:has(input:checked) {
      background: #ead8fa;
      border-color: #a76acb;
    }

    button {
      display: block;
      width: 100%;
      padding: 15px;
      border: none;
      border-radius: 14px;
      background: linear-gradient(135deg, #a66bd0, #8950b5);
      color: white;
      font-size: 1.05rem;
      font-weight: bold;
      cursor: pointer;
      margin: 25px 0;
      transition: 0.2s;
    }

    button:hover {
      transform: translateY(-2px);
      box-shadow: 0 5px 15px rgba(137, 80, 181, 0.25);
    }

    button:disabled {
      opacity: 0.6;
      cursor: wait;
      transform: none;
    }

    #message {
      display: none;
      text-align: center;
      background: white;
      padding: 25px;
      border-radius: 18px;
      color: #8950b5;
      font-weight: bold;
      margin-top: 20px;
    }

    .footer {
      text-align: center;
      color: #967ca5;
      padding: 15px;
      font-size: 0.9rem;
    }

    @media (max-width: 500px) {
      header h1 {
        font-size: 1.8rem;
      }

      .question-card {
        padding: 18px;
      }
    }
  </style>
</head>

<body>
  <div class="container">

    <header>
      <div class="decoration">🎀 💜 💋</div>
      <h1>BB's Preferences</h1>
      <p>A little questionnaire to get to know your preferences better ♡</p>
      <div class="decoration">💕 🌷 💜</div>
    </header>

    <form id="preferencesForm">

      <div id="questions"></div>

      <button type="submit" id="submitBtn">
        Submit Your Answers 💜
      </button>

    </form>

    <div id="message">
      Thank you for answering! 💜🎀<br><br>
      Your preferences have been submitted. mwawawawmam! 💋
    </div>

    <div class="footer">
      Made with love for BB AHHHHHHHHHH O3O ♡
    </div>

  </div>

  <script>
    // Replace this with your Google Apps Script Web App URL.
    const SCRIPT_URL = "https://script.google.com/macros/s/AKfycbzmSpIGTB3K7QQ2d-sI3Fv2KGuY4Z-J_4hQraVfAxv4Uy7aq8ctLBn1-WozuopXbZgR/exec";

    const questions = [

      {
        id: "dateTime",
        title: "♡ What time would you prefer to go on a date?",
        type: "radio",
        options: [
          "Morning 🌅",
          "Afternoon ☀️",
          "Evening 🌆",
          "Late night 🌙"
        ]
      },

      {
        id: "dateDuration",
        title: "♡ How long would you like our date to last?",
        type: "radio",
        options: [
          "A quick date, around 1–2 hours",
          "Half a day",
          "The whole day",
          "A date that lasts until late at night"
        ]
      },

      {
        id: "favoritePlaces",
        title: "♡ Which places would you enjoy visiting?",
        type: "checkbox",
        options: [
          "Beach 🏖️",
          "Park 🌳",
          "Mall 🛍️",
          "Amusement park 🎡",
          "Museum 🖼️",
          "Bookstore 📚",
          "Cafe shop ☕",
          "Mountain or scenic viewpoint 🏞️"
        ]
      },

      {
        id: "dateSetting",
        title: "♡ What kind of place would you prefer for a date?",
        type: "radio",
        options: [
          "Somewhere peaceful and quiet 🌷",
          "Somewhere scenic with a beautiful view 🌅",
          "Somewhere cozy and comfortable 🧸"
        ]
      },

      {
        id: "romanticDates",
        title: "♡ Which romantic dates would you enjoy?",
        type: "checkbox",
        options: [
          "Picnic together 🧺",
          "Watching the sunset 🌇",
          "A romantic movie date 🎬",
          "A walk along the beach 🌊",
          "Dancing together 💃",
          "A scenic nighttime walk 🌙",
        ]
      },

      {
        id: "cozyActivities",
        title: "♡ Which cozy activities would you wan do? xc",
        type: "checkbox",
        options: [
          "#!/bin/bash

# Arrays to store student names and grades
declare -a names
declare -a grades
declare -a highest_students
declare -a lowest_students

count=0

# Input 10 valid students
while [ $count -lt 10 ]; do
    echo ""
    echo "Student $((count + 1))"

    read -p "Enter student name: " name

    # Validate grade input
    while true; do
        read -p "Enter grade (50-100): " grade

        if ! [[ "$grade" =~ ^[0-9]+$ ]]; then
            echo "Warning: Invalid input! Enter numbers only."
        elif [ "$grade" -lt 50 ] || [ "$grade" -gt 100 ]; then
            echo "Warning: Grade must be between 50 and 100."
        else
            break
        fi
    done

    # Store valid inputs in arrays
    names[$count]="$name"
    grades[$count]=$grade

    count=$((count + 1))
done

# Determine highest and lowest grades
highest=${grades[0]}
lowest=${grades[0]}

for ((i = 1; i < 10; i++)); do
    if [ "${grades[$i]}" -gt "$highest" ]; then
        highest=${grades[$i]}
    fi

    if [ "${grades[$i]}" -lt "$lowest" ]; then
        lowest=${grades[$i]}
    fi
done

# Store students with highest and lowest grades
for ((i = 0; i < 10; i++)); do
    if [ "${grades[$i]}" -eq "$highest" ]; then
        highest_students+=("${names[$i]}")
    fi

    if [ "${grades[$i]}" -eq "$lowest" ]; then
        lowest_students+=("${names[$i]}")
    fi
done

# Write results to a text file
{
    echo "===== STUDENT GRADE REPORT ====="
    echo ""
    echo "STUDENT NAMES AND GRADES"

    for ((i = 0; i < 10; i++)); do
        echo "${names[$i]} - ${grades[$i]}"
    done

    echo ""
    echo "HIGHEST GRADE: $highest"
    echo "STUDENT(S) WITH HIGHEST GRADE:"

    for student in "${highest_students[@]}"; do
        echo "$student"
    done

    echo ""
    echo "LOWEST GRADE: $lowest"
    echo "STUDENT(S) WITH LOWEST GRADE:"

    for student in "${lowest_students[@]}"; do
        echo "$student"
    done

} > student_grades_report.txt

echo ""
echo "Grades processed successfully!"
echo "Results saved to student_grades_report.txt"",
          "Playing board games 🎲",
          "Cooking or baking together 🍰",
          "Playing video games 🎮",
          "Listening to music together 🎧",
          "Reading books together 📖",
          "Just talking and spending time together 💗"
        ]
      },

      {
        id: "creativeDates",
        title: "♡ Which creative or unique date u wan xc?",
        type: "checkbox",
        options: [
          "Pottery or craft activities 🏺",
          "Taking pictures together 📸",
          "Visiting an art gallery 🖼️",
          "Trying a new hobby together 🧶",
          "Exploring a new place 🗺️"
        ]
      },

      {
        id: "qualityTime",
        title: "♡ What dit wod u remember mos ouo?",
        type: "radio",
        options: [
          "Having meaningful conversations 💬",
          "Laughing and having fun together 😂",
          "Trying something new together ✨",
          "Making beautiful memories together 📷",
          "#!/bin/bash

# Arrays to store student names and grades
declare -a names
declare -a grades
declare -a highest_students
declare -a lowest_students

count=0

# Input 10 valid students
while [ $count -lt 10 ]; do
    echo ""
    echo "Student $((count + 1))"

    read -p "Enter student name: " name

    # Validate grade input
    while true; do
        read -p "Enter grade (50-100): " grade

        if ! [[ "$grade" =~ ^[0-9]+$ ]]; then
            echo "Warning: Invalid input! Enter numbers only."
        elif [ "$grade" -lt 50 ] || [ "$grade" -gt 100 ]; then
            echo "Warning: Grade must be between 50 and 100."
        else
            break
        fi
    done

    # Store valid inputs in arrays
    names[$count]="$name"
    grades[$count]=$grade

    count=$((count + 1))
done

# Determine highest and lowest grades
highest=${grades[0]}
lowest=${grades[0]}

for ((i = 1; i < 10; i++)); do
    if [ "${grades[$i]}" -gt "$highest" ]; then
        highest=${grades[$i]}
    fi

    if [ "${grades[$i]}" -lt "$lowest" ]; then
        lowest=${grades[$i]}
    fi
done

# Store students with highest and lowest grades
for ((i = 0; i < 10; i++)); do
    if [ "${grades[$i]}" -eq "$highest" ]; then
        highest_students+=("${names[$i]}")
    fi

    if [ "${grades[$i]}" -eq "$lowest" ]; then
        lowest_students+=("${names[$i]}")
    fi
done

# Write results to a text file
{
    echo "===== STUDENT GRADE REPORT ====="
    echo ""
    echo "STUDENT NAMES AND GRADES"

    for ((i = 0; i < 10; i++)); do
        echo "${names[$i]} - ${grades[$i]}"
    done

    echo ""
    echo "HIGHEST GRADE: $highest"
    echo "STUDENT(S) WITH HIGHEST GRADE:"

    for student in "${highest_students[@]}"; do
        echo "$student"
    done

    echo ""
    echo "LOWEST GRADE: $lowest"
    echo "STUDENT(S) WITH LOWEST GRADE:"

    for student in "${lowest_students[@]}"; do
        echo "$student"
    done

} > student_grades_report.txt

echo ""
echo "Grades processed successfully!"
echo "Results saved to student_grades_report.txt""
        ]
      }

    ];

    const questionsContainer = document.getElementById("questions");

    questions.forEach((question, index) => {
      const card = document.createElement("div");
      card.className = "question-card";

      const heading = document.createElement("h2");
      heading.textContent = `${index + 1}. ${question.title}`;
      card.appendChild(heading);

      question.options.forEach((option, optionIndex) => {
        const label = document.createElement("label");
        label.className = "option";

        const input = document.createElement("input");
        input.type = question.type;
        input.name = question.id;
        input.value = option;

        if (question.type === "checkbox") {
          input.name = question.id;
        }

        label.appendChild(input);
        label.appendChild(document.createTextNode(option));
        card.appendChild(label);
      });

      questionsContainer.appendChild(card);
    });

    document.getElementById("preferencesForm")
      .addEventListener("submit", async function(event) {

        event.preventDefault();

        const answers = {};

        for (const question of questions) {
          const selected = document.querySelectorAll(
            `input[name="${question.id}"]:checked`
          );

          if (selected.length === 0) {
            alert("Please answer every question first! 💜");

            const firstOption = document.querySelector(
              `input[name="${question.id}"]`
            );

            firstOption.closest(".question-card").scrollIntoView({
              behavior: "smooth",
              block: "center"
            });

            return;
          }

          if (question.type === "checkbox") {
            answers[question.title] = Array.from(selected).map(
              item => item.value
            );
          } else {
            answers[question.title] = selected[0].value;
          }
        }

        const submitBtn = document.getElementById("submitBtn");
        submitBtn.disabled = true;
        submitBtn.textContent = "Submitting... 💜";

        try {
          if (SCRIPT_URL === "YOUR_GOOGLE_APPS_SCRIPT_URL") {
            alert("Please connect your Google Sheets URL first!");
            submitBtn.disabled = false;
            submitBtn.textContent = "Submit Your Answers 💜";
            return;
          }

          await fetch(SCRIPT_URL, {
            method: "POST",
            mode: "no-cors",
            headers: {
              "Content-Type": "text/plain;charset=utf-8"
            },
            body: JSON.stringify({ answers: answers })
          });

          document.getElementById("preferencesForm").style.display = "none";
          document.getElementById("message").style.display = "block";

          window.scrollTo({
            top: 0,
            behavior: "smooth"
          });

        } catch (error) {
          alert("Something went wrong. Please try again! 💜");
          submitBtn.disabled = false;
          submitBtn.textContent = "Submit Your Answers 💜";
        }
      });
  </script>

</body>
</html>

