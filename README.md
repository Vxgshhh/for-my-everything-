<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>6 Months with My Love</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #f8f9fa;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            padding: 20px;
            overflow: hidden;
        }
        #container {
            background: rgb(42,4,4);
background: linear-gradient(90deg, rgba(42,4,4,1) 0%, rgba(255,0,0,1) 50%, rgba(37,3,3,1) 100%);
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            max-width: 90%;
            transition: transform 0.3s ease-in-out;
        }
        #text {
            font-size: 18px;
            margin-bottom: 20px;
            text-align: left;
            white-space: pre-wrap;
            opacity: 0;
            animation: fadeIn 1s forwards;
        }
        button {
            background-color: #ff4d6d;
            color: white;
            border: none;
            padding: 10px 20px;
            font-size: 16px;
            border-radius: 5px;
            cursor: pointer;
            margin: 5px;
            opacity: 0;
            animation: fadeIn 1s forwards;
            animation-delay: 0.5s;
        }
        button:hover {
            background-color: #e63b5a;
        }
        .f1-theme {
            background-color: #d1071d;
            color: white;
            padding: 20px;
            font-size: 22px;
            text-align: center;
            position: relative;
            animation: slideInLeft 0.5s forwards;
        }
        .crocheting-theme {
            background-color: #f7c6c2;
            color: #004f29;
            padding: 20px;
            font-size: 22px;
            text-align: center;
            position: relative;
            animation: slideInRight 0.5s forwards;
        }
        .debating-theme {
            background-color: #173b3c;
            color: #ffcc00;
            padding: 20px;
            font-size: 22px;
            text-align: center;
            position: relative;
            animation: bounceUp 0.5s forwards;
        }
        .valentine-theme {
            background-color: #ff69b4;
            color: white;
            padding: 20px;
            font-size: 22px;
            text-align: center;
            position: relative;
            animation: fadeIn 0.5s forwards;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
            }
            to {
                opacity: 1;
            }
        }

        @keyframes slideInLeft {
            from {
                transform: translateX(-100%);
            }
            to {
                transform: translateX(0);
            }
        }

        @keyframes slideInRight {
            from {
                transform: translateX(100%);
            }
            to {
                transform: translateX(0);
            }
        }

        @keyframes bounceUp {
            from {
                transform: translateY(100%);
            }
            to {
                transform: translateY(0);
            }
        }
    </style>
</head>
<body>
    <div id="container">
        <div id="slide">
            <p id="text">Loading...</p>
            <button id="nextButton" onclick="nextSlide()">Next</button>
        </div>
    </div>

    <script>
        let slides = [
            // First Slide: F1 Theme
            `<div class="f1-theme">
                now, where do i even start? of course, with the elephant in our room, 6 MONTHS, 6 WHOLE MONTHS WITH THE WOMAN I LOVE HSHSHS. from the very first month of us talking, i knew i wanted this fascinating, one-of-a-kind girl to be mine. you were unlike anyone i had ever met, your cute little wine story, our calls when you went to bangalore, our movie nights (where we never actually watched anything, just yapped away hehe). every moment with you stuck with me, and it always will. youâ€™ve shaped me into the boy i am today, and iâ€™ll always be endlessly grateful for that.
            </div>`,

            // Second Slide: F1 Theme
            `<div class="f1-theme">
                SECOND MONTH WITH MY ELLAM ELLAM, ahhh, i love reminiscing about everything weâ€™ve done. you were the first to wish me on my birthday, and that was also the first time you ever called me baby (unironically ðŸ™„). thatâ€™s when our plans for your india trip started taking shape, and our calls became even more consistent, more movies, more flirting, more us. may was filled with so many beautiful moments, and every second i spent with you then, and every second iâ€™ll spend with you moving forward, will always be my favorite.
            </div>`,

            // Third Slide: Crocheting Theme
            `<div class="crocheting-theme">
                THIRD MONTH, INDIA TIMEEEEE! this was when you finally came to india, and WHERE DO I EVEN BEGIN? our cash inc games (and it constantly crashing your wifi ðŸ¤£ðŸ¤£), watching IPL together (and RCB losing ðŸ¤£ðŸ¤£), i was never really a cricket fan, you know, but watching it with you made me feel like i had been one forever. our india planning only got stronger, and i was the happiest boy in the world because with every passing day, i was getting closer to meeting the woman i wanted to spend forever with.
            </div>`,

            // Fourth Slide: Crocheting Theme
            `<div class="crocheting-theme">
                4TH MONTH, THE HAPPIEST TIME OF MY LIFE. there i was, waking up at the crack of dawn, ready to travel all the way to kochi. amma dropped me at the bus stand, and that ride? it was the best i had ever felt in my life, texting my ellam ellam the entire way. kochi was my everything, and it still is. on my way back, i kept thinking, "just like that, i know who to love for the rest of my life." the days that followed only made my love for you grow faster and deeper. and yes, the uncertainty of me coming to dubai weighed on us, but that didnâ€™t stop me from falling even harder.
            </div>`,

            // Fifth Slide: Debating Theme
            `<div class="debating-theme">
                now letâ€™s talk about august, shall we? WE STARTED DATINGGGGGG (after declaring again, hehe). we were ready to face the distance that knocked on our door, and since then, iâ€™ve been committed to the woman i always dreamed of being with. i know the next few months were tough, but we made it through, didnâ€™t we? it only proved that no matter how hard things got, weâ€™d always find a way back to each other. thereâ€™s something about you that makes me fall harder every single day, your smile, your voice, the way youâ€™re such a kurumbi for me, how incredibly cultured you are (i always wanted a girl whoâ€™s at my mallu level, if not more, and you absolutely are, you pandi). everything about us makes me realize how beautiful life truly is, and that has led us to our
            </div>`,

            // Sixth Slide: Debating Theme
            `<div class="debating-theme">
                6 MONTH ANNIVERSARY, 6 MONTHS WITH THIS ONE LITTLE NATAK KURUMBI RAANI. oh god, iâ€™m elated, happier than iâ€™ve ever been. you have no idea how hard iâ€™m smiling while writing this, and i hope youâ€™re smiling while reading it, knowing that you, this girl from irinjalakuda and kottayam, became the woman i love, my support system, my source of happiness... and the list goes on (let me be, iâ€™m a man in love). speaking of 6 months, valentineâ€™s day is coming up, isnâ€™t it? ðŸ¤” and thereâ€™s only one girl on my mind. in true ok kanmani fashion, would you like to declare yourself as my kanmani for valentineâ€™s? can my kurumbi be my valentine? iâ€™d be the happiest boy ever if you said yes, so go ahead and answer the poll below ðŸ¤­
            </div>`,

            // Final Slide: Valentine Theme
            `<div class="valentine-theme">
                <p>Will my kurumbi be my valentine?</p>
                <button onclick="showFinalMessage()">Yes</button>
                <button onclick="showFinalMessage()">Yes</button>
            </div>`
        ];

        let currentSlide = 0;
        let textElement = document.getElementById("text");
        let nextButton = document.getElementById("nextButton");

        function nextSlide() {
            if (currentSlide < slides.length - 1) {
                currentSlide++;
                textElement.innerHTML = slides[currentSlide];
            } else {
                showValentineOptions();
            }
        }

        function showValentineOptions() {
            document.getElementById("slide").innerHTML = `
                <p>Will my kurumbi be my valentine?</p>
                <button onclick="showFinalMessage()">Yes</button>
                <button onclick="showFinalMessage()">Yes</button>
            `;
        }

        function showFinalMessage() {
            document.getElementById("slide").innerHTML = `
                <p>HEHEHEHEHHEE I KNEW IT. HI VALENTINEEEEE! i love you so, so, so, so much, and YOU BETTER BE GIVING ME UMMAS RIGHT NOW BECAUSE THATâ€™S EXACTLY WHAT Iâ€™M DOING TOO. smile, my love. i hope you know that i will always be a proud boyfriend, how could i not be? youâ€™re the strongest girl i know (not physically, though, iâ€™ll still beat your ass). UMMMMMMAAAAA!</p>
            `;
        }

        window.onload = function() {
            textElement.innerHTML = slides[currentSlide];
        };
    </script>
</body>
</html>
