
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Our Date Planner ♡</title>

<style>
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    font-family: Arial, sans-serif;
    background: #fff5f7;
    color: #49343c;
}

header {
    text-align: center;
    padding: 45px 15px 30px;
    background: linear-gradient(135deg, #ffdce7, #fff0f3);
}

header h1 {
    font-size: 36px;
    color: #d65c83;
    margin: 0 0 10px;
}

header p {
    color: #805b69;
}

.container {
    max-width: 850px;
    margin: 25px auto;
    padding: 15px;
}

.card {
    background: white;
    padding: 25px;
    border-radius: 16px;
    margin-bottom: 20px;
    box-shadow: 0 4px 15px rgba(150, 70, 100, 0.07);
}

h2 {
    color: #d65c83;
    margin-top: 0;
}

h3 {
    margin-bottom: 10px;
    font-size: 16px;
}

.question {
    margin-bottom: 25px;
}

.choices {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
    gap: 10px;
}

.choice {
    display: block;
    padding: 13px;
    border: 1px solid #f1d5df;
    border-radius: 10px;
    cursor: pointer;
    transition: 0.2s;
    background: white;
}

.choice:hover {
    background: #fff0f5;
    border-color: #df83a2;
}

.choice:has(input:checked) {
    background: #ffe5ed;
    border: 2px solid #dc7194;
    color: #b83e69;
}

.choice input {
    margin-right: 7px;
    accent-color: #d65c83;
}

select {
    width: 100%;
    padding: 13px;
    border: 1px solid #edcbd7;
    border-radius: 9px;
    background: white;
    font-size: 15px;
    color: #49343c;
}

button {
    width: 100%;
    padding: 15px;
    border: none;
    border-radius: 10px;
    background: #d65c83;
    color: white;
    font-size: 16px;
    font-weight: bold;
    cursor: pointer;
}

button:hover {
    background: #bd456d;
}

.results {
    display: none;
    background: #fff0f5;
    padding: 20px;
    border-radius: 12px;
    margin-top: 20px;
    line-height: 1.7;
}

.match {
    padding: 12px;
    background: white;
    border-radius: 9px;
    margin: 8px 0;
}

footer {
    text-align: center;
    padding: 30px;
    color: #a27b89;
    font-size: 13px;
}

.section-label {
    color: #d65c83;
    font-size: 12px;
    font-weight: bold;
    letter-spacing: 2px;
    margin-bottom: 8px;
}

@media(max-width: 500px) {
    header h1 {
        font-size: 29px;
    }

    .card {
        padding: 18px;
    }
}
</style>
</head>

<body>

<header>
    <div style="font-size:35px">♡</div>
    <h1>Our Date Planner</h1>
    <p>Let's find the perfect date for us!</p>
    <p>Two people. One plan. Endless possibilities.</p>
</header>

<div class="container">

    <div class="card">
        <div class="section-label">STEP 01</div>
        <h2>💕 Person A's Preferences</h2>
        <div id="personA"></div>
    </div>

    <div class="card">
        <div class="section-label">STEP 02</div>
        <h2>💗 Person B's Preferences</h2>
        <div id="personB"></div>
    </div>

    <div class="card">
        <div class="section-label">STEP 03</div>
        <h2>✨ Find Our Perfect Date</h2>
        <p>Compare your answers and discover what you both like!</p>
        <button onclick="compareAnswers()">Find Our Match ♡</button>
        <div id="results" class="results"></div>
    </div>

</div>

<footer>
    Made with love ♡ Our Date Planner
</footer>

<script>

// ===================================
// EDIT YOUR QUESTIONS AND CHOICES HERE
// ===================================

const questions = [
    {
        id: "mood",
        title: "What's your mood?",
        type: "radio",
        options: [
            "💕 Romantic",
            "🎢 Adventurous",
            "☁️ Chill and cozy",
            "✨ Spontaneous",
            "🎉 Fun and exciting",
            "🌿 Peaceful and relaxing"
        ]
    },

    {
        id: "budget",
        title: "What's our budget?",
        type: "radio",
        options: [
            "Free",
            "₱100 - ₱300",
            "₱300 - ₱500",
            "₱500 - ₱1,000",
            "₱1,000 - ₱2,000",
            "₱2,000+"
        ]
    },

    {
        id: "place",
        title: "Where do you want to go?",
        type: "radio",
        options: [
            "🏠 Indoor",
            "🌳 Outdoor",
            "🌊 Beach",
            "🏙️ City",
            "Anywhere!"
        ]
    },

    {
        id: "time",
        title: "What time should we go?",
        type: "radio",
        options: [
            "🌅 Morning",
            "☀️ Afternoon",
            "🌇 Evening",
            "🌙 Late night",
            "Anytime!"
        ]
    },

    {
        id: "weather",
        title: "What's the weather preference?",
        type: "radio",
        options: [
            "☀️ Sunny",
            "🌧️ Rainy",
            "☁️ Cloudy",
            "❄️ Cold weather",
            "Doesn't matter!"
        ]
    },

    {
        id: "duration",
        title: "How long should our date be?",
        type: "radio",
        options: [
            "1-2 hours",
            "3-4 hours",
            "Half a day",
            "Whole day",
            "Overnight"
        ]
    },

    {
        id: "activities",
        title: "What activities would you enjoy?",
        subtitle: "You can select multiple answers!",
        type: "checkbox",
        options: [
            "Coffee shop date",
            "Fast food date",
            "Street food adventure",
            "Samgyupsal date",
            "Ramen date",
            "Pizza date",
            "Milktea date",
            "Dessert and cake date",
            "Fine dining",
            "Late-night food trip",
            "Ice cream date",
            "Picnic with homemade food",
            "Cooking together",
            "Buffet date",
            "Trying a new restaurant",

            "Watching the sunset",
            "Stargazing",
            "Candlelight dinner",
            "Night walk",
            "Beach date",
            "Rooftop date",
            "Watching the sunrise",
            "Flower shopping",
            "Couple photoshoot",
            "Writing love letters",
            "Recreating our first date",
            "Watching city lights",

            "Amusement park",
            "Arcade date",
            "Bowling",
            "Go-kart racing",
            "Billiards",
            "Karaoke",
            "Escape room",
            "Trampoline park",
            "Hiking",
            "Cycling",
            "Swimming",
            "Roller skating",
            "Visiting a zoo",
            "Trying a new sport",
            "Road trip",

            "Movie marathon",
            "Playing video games",
            "Board game night",
            "Baking cookies",
            "Cooking a new recipe",
            "Building LEGO",
            "Painting together",
            "Doing a puzzle",
            "Watching anime",
            "Reading books",
            "Having a sleepover",
            "Making a blanket fort",
            "Listening to music",
            "DIY project",

            "Pottery painting",
            "Thrift shopping",
            "Art gallery",
            "Museum date",
            "Making matching bracelets",
            "Creating a scrapbook",
            "Taking random photographs",
            "Painting each other's portraits",
            "Making a bucket list",
            "Bookstore date",
            "Trying perfumes",
            "Making a time capsule",
            "Decorating phone cases",
            "Flower arranging",

            "Walking in the park",
            "Convenience store food trip",
            "Window shopping",
            "Exploring a new neighborhood",
            "Playing mobile games",
            "Making homemade coffee",
            "Visiting a public market",
            "Watching free events",
            "Deep-talk night",
            "Spontaneous walk"
        ]
    }
];

// ===================================
// DISPLAY THE QUESTIONS
// ===================================

function createQuestions(person, containerId) {

    const container = document.getElementById(containerId);

    questions.forEach(q => {

        let html = `
            <div class="question">
                <h3>${q.title}</h3>
                ${q.subtitle ? `<p>${q.subtitle}</p>` : ""}
                <div class="choices">
        `;

        q.options.forEach(option => {

            html += `
                <label class="choice">
                    <input
                        type="${q.type}"
                        name="${person}_${q.id}"
                        value="${option}"
                    >
                    ${option}
                </label>
            `;

        });

        html += `
                </div>
            </div>
        `;

        container.innerHTML += html;

    });
}

createQuestions("A", "personA");
createQuestions("B", "personB");

// ===================================
// GET SELECTED ANSWERS
// ===================================

function getAnswers(person) {

    let answers = {};

    questions.forEach(q => {

        const selected = document.querySelectorAll(
            `input[name="${person}_${q.id}"]:checked`
        );

        answers[q.id] = Array.from(selected).map(
            input => input.value
        );

    });

    return answers;
}

// ===================================
// COMPARE BOTH PEOPLE'S ANSWERS
// ===================================

function compareAnswers() {

    const a = getAnswers("A");
    const b = getAnswers("B");

    const results = document.getElementById("results");

    let html = `
        <h2>💕 Your Date Compatibility</h2>
        <p>Here's what you both have in common!</p>
    `;

    let totalMatches = 0;

    questions.forEach(q => {

        const common = a[q.id].filter(
            item => b[q.id].includes(item)
        );

        if (common.length > 0) {

            totalMatches++;

            html += `
                <div class="match">
                    <strong>${q.title}</strong><br>
                    ${common.join("<br>")}
                </div>
            `;

        }

    });

    if (totalMatches === 0) {

        html += `
            <p>You have different preferences!
            Time to discover something new together. ♡</p>
        `;

    } else {

        html += `
            <h3>You matched in ${totalMatches} categories!</h3>
            <p>These are your shared preferences. Pick one and make it happen! ♡</p>
        `;

    }

    results.innerHTML = html;
    results.style.display = "block";

    results.scrollIntoView({
        behavior: "smooth"
    });

}

</script>

</body>
</html>
