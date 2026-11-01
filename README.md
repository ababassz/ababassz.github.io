
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>BB's Preferences ♡</title>

<style>
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    font-family: 'Trebuchet MS', Arial, sans-serif;
    background: #f8f2ff;
    color: #55416d;
}

header {
    text-align: center;
    padding: 55px 15px 45px;
    background: linear-gradient(135deg, #d9c1ff, #f3e7ff, #ead7ff);
    position: relative;
    overflow: hidden;
}

header h1 {
    font-size: 38px;
    color: #8651b9;
    margin: 12px 0;
}

header p {
    color: #795b96;
    line-height: 1.6;
}

.decor {
    font-size: 27px;
    margin: 8px;
}

.container {
    max-width: 820px;
    margin: 25px auto;
    padding: 15px;
}

.card {
    background: white;
    padding: 25px;
    border-radius: 20px;
    margin-bottom: 20px;
    box-shadow: 0 5px 20px rgba(120,70,160,0.08);
    border: 1px solid #eee1ff;
}

.section-number {
    color: #a078ce;
    font-size: 12px;
    font-weight: bold;
    letter-spacing: 2px;
}

h2 {
    color: #9664c5;
    margin-top: 10px;
}

h3 {
    font-size: 16px;
    color: #624b7a;
    margin-bottom: 13px;
}

.question {
    margin-bottom: 30px;
}

.description {
    font-size: 13px;
    color: #a18baa;
    margin-bottom: 16px;
}

.choices {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
    gap: 10px;
}

.choice {
    display: flex;
    align-items: center;
    gap: 9px;
    padding: 14px;
    border: 1px solid #e8d9fa;
    border-radius: 12px;
    cursor: pointer;
    background: #fdfaff;
    font-size: 14px;
    transition: 0.2s;
}

.choice:hover {
    background: #f5eaff;
    transform: translateY(-2px);
}

.choice:has(input:checked) {
    background: #edddff;
    border: 2px solid #a675d5;
    color: #7845a8;
}

.choice input {
    accent-color: #9862c9;
    cursor: pointer;
}

button {
    width: 100%;
    padding: 16px;
    border: none;
    border-radius: 14px;
    background: linear-gradient(135deg, #a879d6, #8e5cbd);
    color: white;
    font-size: 16px;
    font-weight: bold;
    cursor: pointer;
    transition: 0.2s;
}

button:hover {
    transform: translateY(-2px);
    box-shadow: 0 5px 15px #d8bdf1;
}

button:disabled {
    opacity: 0.6;
    cursor: wait;
}

.results {
    display: none;
    padding: 20px;
    background: #f6edff;
    border-radius: 14px;
    margin-top: 20px;
    line-height: 1.7;
    text-align: center;
}

footer {
    text-align: center;
    padding: 30px;
    color: #a68abb;
    font-size: 13px;
}

.divider {
    text-align: center;
    color: #c5a4e7;
    margin: 20px;
    font-size: 20px;
}

@media(max-width: 500px) {
    header h1 {
        font-size: 30px;
    }

    .card {
        padding: 19px;
    }
}
</style>
</head>

<body>

<header>
    <div class="decor">💜 🎀 💋</div>
    <h1>BB's Preferences</h1>
    <p>A little questionnaire made especially for you.</p>
    <p>Let's discover all the things you love! ♡</p>
    <div class="decor">🧸 💌 ✨</div>
</header>

<div class="container">

<form id="preferencesForm">

<div id="questionnaire"></div>

<div class="card">
    <div class="section-number">LAST STEP 💌</div>
    <h2>That's everything, BB! 💜</h2>
    <p class="description">
        Thank you for answering my little questionnaire!
        Your answers will be saved.
    </p>

    <button type="submit" id="submitButton">
        Submit My Preferences 💋
    </button>

    <div class="results" id="result"></div>
</div>

</form>
</div>

<footer>
    Made with love, just for BB 💜<br>
    ♡ 🎀 💋 ♡
</footer>

<script>

// ======================================
// EDIT YOUR QUESTIONS AND CHOICES HERE
// ======================================

const questions = [

{
    section: "01 · PERSONAL VIBES 💜",
    items: [
        {
            id: "mood",
            title: "What kind of date atmosphere do you prefer?",
            type: "radio",
            options: [
                "💕 Romantic and intimate",
                "🎀 Cute and sweet",
                "🌷 Peaceful and relaxing",
                "🎉 Fun and exciting",
                "✨ Adventurous and thrilling",
                "🧸 Cozy and comfortable",
                "🌙 Quiet and private"
            ]
        },
        {
            id: "budget",
            title: "How much would you like to spend on a date?",
            type: "radio",
            options: [
                "💜 Free",
                "₱100 - ₱300",
                "₱300 - ₱500",
                "₱500 - ₱1,000",
                "₱1,000 - ₱1,500",
                "₱1,500 - ₱2,000",
                "₱2,000 - ₱3,000",
                "₱3,000 and above"
            ]
        },
        {
            id: "time",
            title: "What time do you prefer going on dates?",
            type: "radio",
            options: [
                "🌅 6 AM - 9 AM",
                "☀️ 9 AM - 12 PM",
                "🌤️ 12 PM - 3 PM",
                "🌇 3 PM - 6 PM",
                "🌆 6 PM - 9 PM",
                "🌙 9 PM - 12 AM"
            ]
        },
        {
            id: "duration",
            title: "How long should our date last?",
            type: "radio",
            options: [
                "1 - 2 hours",
                "3 - 4 hours",
                "5 - 6 hours",
                "7 - 9 hours",
                "10 - 12 hours",
                "Overnight"
            ]
        },
        {
            id: "weather",
            title: "Which weather do you enjoy for a date?",
            type: "radio",
            options: [
                "☀️ Warm and sunny",
                "☁️ Cool and cloudy",
                "🌧️ Rainy weather",
                "🌤️ Breezy afternoon",
                "🌙 Cool evening"
            ]
        }
    ]
},

{
    section: "02 · PLACES YOU LOVE 📍",
    items: [
        {
            id: "places",
            title: "Which places would you like to visit?",
            type: "checkbox",
            options: [
                "☕ Cozy coffee shops",
                "🍽️ Fancy restaurants",
                "🛍️ Shopping malls",
                "🌊 Beaches",
                "🌳 Parks and gardens",
                "🎢 Amusement parks",
                "🎮 Arcades",
                "🎬 Cinemas",
                "📚 Bookstores",
                "🖼️ Museums and art galleries",
                "🏔️ Mountains",
                "🏙️ City viewpoints",
                "🏨 Hotels and staycations",
                "🌸 Flower gardens",
                "🐠 Aquariums",
                "🦁 Zoos",
                "🎳 Bowling alleys",
                "🎤 Karaoke places",
                "🛒 Night markets",
                "🏕️ Camping sites"
            ]
        },
        {
            id: "transport",
            title: "How would you prefer traveling to our date?",
            type: "radio",
            options: [
                "🚗 Private car",
                "🏍️ Motorcycle ride",
                "🚕 Taxi or Grab",
                "🚌 Bus ride",
                "🚆 Train ride",
                "🚶 Walking together"
            ]
        }
    ]
},

{
    section: "03 · FOOD AND DRINKS 🍓",
    items: [
        {
            id: "food",
            title: "What food would you love to eat on a date?",
            type: "checkbox",
            options: [
                "🍣 Japanese food",
                "🍜 Ramen",
                "🍱 Sushi",
                "🥩 Samgyupsal",
                "🍗 Korean fried chicken",
                "🍲 Korean food",
                "🍕 Pizza",
                "🍔 Burgers",
                "🍟 Fries",
                "🍝 Pasta",
                "🥞 Pancakes",
                "🍰 Cakes",
                "🍩 Donuts",
                "🍦 Ice cream",
                "🧋 Milk tea",
                "☕ Coffee",
                "🍫 Chocolate desserts",
                "🥗 Salads",
                "🍗 Filipino food",
                "🍢 Street food",
                "🥐 Pastries",
                "🍛 Indian food",
                "🌮 Mexican food",
                "🥪 Sandwiches",
                "🍣 Buffet"
            ]
        },
        {
            id: "restaurant",
            title: "What kind of restaurant would you prefer?",
            type: "radio",
            options: [
                "🕯️ Romantic candlelight restaurant",
                "🌸 Cute aesthetic cafe",
                "🏮 Korean BBQ restaurant",
                "🍜 Japanese ramen restaurant",
                "🍽️ Fine dining restaurant",
                "🍔 Casual fast food restaurant",
                "🌃 Rooftop restaurant",
                "🌊 Beachside restaurant",
                "🍰 Dessert cafe"
            ]
        },
        {
            id: "drinks",
            title: "Which drinks do you enjoy?",
            type: "checkbox",
            options: [
                "🧋 Milk tea",
                "☕ Iced coffee",
                "🍵 Matcha",
                "🍫 Hot chocolate",
                "🥤 Fruit smoothies",
                "🍓 Strawberry drinks",
                "🍋 Lemonade",
                "🧃 Fruit juices",
                "🧊 Iced tea",
                "🥛 Milkshakes"
            ]
        }
    ]
},

{
    section: "04 · ROMANTIC ACTIVITIES 🌹",
    items: [
        {
            id: "romantic",
            title: "Which romantic activities would you enjoy?",
            type: "checkbox",
            options: [
                "🌅 Watching the sunset together",
                "🌌 Stargazing",
                "🌷 Receiving flowers",
                "💌 Exchanging handwritten letters",
                "📸 Couple photoshoot",
                "🌊 Beach sunset date",
                "🕯️ Candlelight dinner",
                "🌙 Late-night walks",
                "🌸 Flower picking",
                "🎀 Matching outfits",
                "💕 Recreating our first date",
                "🎡 Ferris wheel ride",
                "🌃 Watching city lights",
                "🧺 Romantic picnic",
                "🎁 Exchanging gifts",
                "💃 Slow dancing",
                "🌅 Watching the sunrise",
                "💗 Making a scrapbook together"
            ]
        }
    ]
},

{
    section: "05 · FUN AND ADVENTURE 🎢",
    items: [
        {
            id: "adventure",
            title: "Which fun activities would you try?",
            type: "checkbox",
            options: [
                "🎢 Roller coaster rides",
                "🎮 Arcade games",
                "🎳 Bowling",
                "🏎️ Go-kart racing",
                "🎤 Karaoke",
                "🛼 Roller skating",
                "🏊 Swimming",
                "🥾 Hiking",
                "🚴 Cycling",
                "🧗 Indoor climbing",
                "🧩 Escape rooms",
                "🎯 Archery",
                "🏸 Badminton",
                "🎾 Tennis",
                "🏕️ Camping",
                "🚗 Road trips",
                "🛶 Kayaking",
                "🏄 Water activities",
                "🎪 Carnival games"
            ]
        }
    ]
},

{
    section: "06 · COZY AND INDOOR DATES 🧸",
    items: [
        {
            id: "indoor",
            title: "Which indoor activities would you enjoy?",
            type: "checkbox",
            options: [
                "🎬 Movie marathon",
                "🎮 Playing video games",
                "🍪 Baking cookies together",
                "🍳 Cooking together",
                "🎨 Painting together",
                "🧩 Completing puzzles",
                "🧸 Building LEGO",
                "📺 Watching anime",
                "🎲 Board games",
                "📖 Reading books",
                "🎧 Listening to music",
                "🏠 Indoor picnic",
                "🛏️ Cozy movie night",
                "📸 Looking through old pictures",
                "💅 Doing each other's nails",
                "🎀 Making bracelets",
                "🖍️ Coloring together",
                "🧁 Decorating cupcakes"
            ]
        }
    ]
},

{
    section: "07 · CREATIVE AND UNIQUE DATES 🎨",
    items: [
        {
            id: "creative",
            title: "Which unique experiences would you like?",
            type: "checkbox",
            options: [
                "🏺 Pottery painting",
                "🖼️ Art workshop",
                "📷 Photography walk",
                "🛍️ Thrift shopping",
                "📚 Bookstore exploration",
                "🌸 Flower arranging",
                "🧶 DIY crafts",
                "🎨 Painting each other's portraits",
                "💍 Making matching accessories",
                "📔 Scrapbooking",
                "🧸 Plushie shopping",
                "🕯️ Candle making",
                "🧴 Perfume making",
                "🍰 Cake decorating",
                "🎀 Decorating phone cases",
                "🛒 Shopping challenge"
            ]
        }
    ]
},

{
    section: "08 · SIMPLE AND BUDGET-FRIENDLY DATES 💜",
    items: [
        {
            id: "simple",
            title: "Which simple dates would you enjoy?",
            type: "checkbox",
            options: [
                "🚶 Walking around the park",
                "🥤 Convenience store food trip",
                "🌅 Watching the sunset",
                "🧋 Buying milk tea together",
                "🛍️ Window shopping",
                "🍟 Sharing street food",
                "🧺 Homemade picnic",
                "📸 Taking random pictures",
                "🎮 Playing mobile games",
                "🌳 Visiting a public garden",
                "🍳 Cooking a homemade meal",
                "💬 Deep conversations",
                "🌙 Evening stroll",
                "📚 Visiting a public library",
                "🎵 Listening to music together"
            ]
        }
    ]
},

{
    section: "09 · LITTLE PERSONAL DETAILS 💋",
    items: [
        {
            id: "gifts",
            title: "What kind of gifts would make you happy?",
            type: "checkbox",
            options: [
                "💐 Flowers",
                "🧸 Plushies",
                "💍 Jewelry",
                "🎀 Accessories",
                "👜 Bags",
                "👗 Clothes",
                "🌸 Perfume",
                "🍫 Chocolates",
                "💌 Handwritten letters",
                "📸 Printed photographs",
                "🧴 Skincare products",
                "🎨 Handmade gifts",
                "🍰 Desserts",
                "📚 Books"
            ]
        },
        {
            id: "surprises",
            title: "Which surprises would you love?",
            type: "checkbox",
            options: [
                "💐 Surprise flower delivery",
                "🎂 Surprise birthday celebration",
                "🍽️ Secret dinner reservation",
                "🎁 Unexpected gifts",
                "💌 Hidden love letters",
                "🧺 Surprise picnic",
                "🎬 Surprise movie date",
                "🧸 Surprise plushie",
                "📸 A collection of our pictures",
                "🌹 A romantic room decoration"
            ]
        }
    ]
}

];

// ======================================
// GENERATE THE QUESTIONNAIRE
// ======================================

const questionnaire = document.getElementById("questionnaire");

questions.forEach((section, sectionIndex) => {

    let html = `
    <div class="card">
        <div class="section-number">${section.section}</div>
    `;

    section.items.forEach(q => {

        html += `
        <div class="question">
            <h3>${q.title}</h3>
            <p class="description">
                ${q.type === "checkbox"
                    ? "♡ Select all the ones you like!"
                    : "♡ Choose your preferred answer."}
            </p>
            <div class="choices">
        `;

        q.options.forEach((option, index) => {

            html += `
            <label class="choice">
                <input
                    type="${q.type}"
                    name="${q.id}"
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

    });

    html += `</div>`;

    questionnaire.innerHTML += html;

});

// ======================================
// GOOGLE SHEETS CONNECTION
// ======================================

// Paste your Google Apps Script /exec URL here.
const SCRIPT_URL = "PASTE_YOUR_WEB_APP_URL_HERE";

// ======================================
// SUBMIT BB'S ANSWERS
// ======================================

document.getElementById("preferencesForm")
.addEventListener("submit", async function(event) {

    event.preventDefault();

    const answers = {};
    let missing = [];

    questions.forEach(section => {

        section.items.forEach(q => {

            const selected = document.querySelectorAll(
                `input[name="${q.id}"]:checked`
            );

            answers[q.id] = Array.from(selected).map(
                input => input.value
            );

            if (answers[q.id].length === 0) {
                missing.push(q.title);
            }

        });

    });

    if (missing.length > 0) {
        alert("Please answer all questions first, BB! 💜\n\nMissing: " + missing.join(", "));
        return;
    }

    if (SCRIPT_URL === "PASTE_YOUR_WEB_APP_URL_HERE") {
        alert("The Google Sheets connection has not been configured yet! 💜");
        return;
    }

    const button = document.getElementById("submitButton");
    const result = document.getElementById("result");

    button.disabled = true;
    button.textContent = "Saving your answers... 💜";

    try {

        await fetch(SCRIPT_URL, {
            method: "POST",
            mode: "no-cors",
            headers: {
                "Content-Type": "text/plain;charset=utf-8"
            },
            body: JSON.stringify({
                answers: answers
            })
        });

        result.style.display = "block";
        result.innerHTML = `
            <h2>Thank you, BB! 💜</h2>
            <p>Your answers have been sent!</p>
            <div style="font-size:35px">🎀 💋 🧸</div>
            <p>Made with love, just for you. ♡</p>
        `;

        button.textContent = "Submitted! 💜";

    } catch(error) {

        alert("Something went wrong. Please try again!");

        button.disabled = false;
        button.textContent = "Submit My Preferences 💋";

    }

});

</script>

</body>
</html>
