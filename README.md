<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ESL Vocabulary Exercise</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #f0f8ff;
            margin: 0;
            padding: 20px;
            color: #333;
        }
        .container {
            max-width: 800px;
            margin: 0 auto;
            background-color: white;
            border-radius: 15px;
            padding: 25px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
        }
        h1, h2 {
            color: #008080;
        }
        .nav-buttons {
            display: flex;
            justify-content: space-between;
            margin-bottom: 20px;
            flex-wrap: wrap;
        }
        button {
            background: linear-gradient(135deg, #4CAF90, #008080);
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 8px;
            cursor: pointer;
            font-size: 14px;
            transition: all 0.3s;
        }
        button:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        }
        .score {
            font-size: 18px;
            font-weight: bold;
            color: #008080;
            margin-left: auto;
        }
        .section {
            display: none;
        }
        .section.active {
            display: block;
        }
        .vocab-item {
            background: linear-gradient(135deg, #e6f7ff, #b3f0ff);
            border-left: 5px solid #008080;
            padding: 15px;
            margin-bottom: 15px;
            border-radius: 8px;
        }
        .word-bank {
            background: linear-gradient(135deg, #4CAF90, #008080);
            color: white;
            padding: 15px;
            border-radius: 8px;
            margin-bottom: 20px;
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }
        .word-bank div {
            background: rgba(255, 255, 255, 0.2);
            padding: 8px 12px;
            border-radius: 5px;
            cursor: pointer;
            transition: all 0.2s;
        }
        .word-bank div:hover {
            background: rgba(255, 255, 255, 0.3);
        }
        .sentence {
            background: #f9f9f9;
            padding: 15px;
            border-radius: 8px;
            margin-bottom: 15px;
            border-left: 4px solid #4CAF90;
        }
        input[type="text"] {
            padding: 8px;
            border: 1px solid #ddd;
            border-radius: 4px;
            width: 150px;
        }
        .match-container {
            display: flex;
            justify-content: space-between;
            margin-bottom: 20px;
        }
        .match-column {
            width: 48%;
            background: #f9f9f9;
            padding: 15px;
            border-radius: 8px;
        }
        .match-item {
            padding: 10px;
            margin-bottom: 10px;
            border-radius: 5px;
            cursor: pointer;
            transition: all 0.2s;
        }
        .match-item:hover {
            background: #e6f7ff;
        }
        .correct {
            background-color: #d4edda !important;
            color: #155724;
        }
        .incorrect {
            background-color: #f8d7da !important;
            color: #721c24;
        }
        .selected {
            background-color: #d1ecf1 !important;
        }
        .feedback {
            margin-top: 5px;
            font-size: 14px;
            font-style: italic;
        }
        .microphone-btn {
            background: linear-gradient(135deg, #ff6b6b, #ee5a24);
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-left: 10px;
        }
        .pronunciation-input {
            display: inline-flex;
            align-items: center;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="score">Score: 0 / 12</div>
        <div class="nav-buttons">
            <button onclick="showSection('vocabulary')">Vocabulary List</button>
            <button onclick="showSection('writing')">Fill in the Gaps (Writing)</button>
            <button onclick="showSection('matching')">Match Definitions</button>
            <button onclick="showSection('pronunciation')">Fill in the Gaps (Pronunciation)</button>
        </div>

        <!-- Vocabulary List Section -->
        <div id="vocabulary" class="section active">
            <h2>Vocabulary List</h2>
            <div class="vocab-item">
                <h3>unfortunately <button onclick="speak('unfortunately')">▶️ Hear</button></h3>
                <p><strong>Context:</strong> expressing regret or disappointment</p>
                <p><strong>Meaning:</strong> used to express sadness, regret, or disappointment about something</p>
                <p><strong>Example:</strong> Unfortunately, the event was canceled due to rain.</p>
            </div>
            <div class="vocab-item">
                <h3>capacity <button onclick="speak('capacity')">▶️ Hear</button></h3>
                <p><strong>Context:</strong> ability to contain or produce</p>
                <p><strong>Meaning:</strong> the maximum amount that something can contain or produce</p>
                <p><strong>Example:</strong> The stadium has a capacity of 50,000 people.</p>
            </div>
            <div class="vocab-item">
                <h3>awareness <button onclick="speak('awareness')">▶️ Hear</button></h3>
                <p><strong>Context:</strong> knowledge or understanding</p>
                <p><strong>Meaning:</strong> knowledge or understanding of a subject, issue, or situation</p>
                <p><strong>Example:</strong> There is a growing awareness of environmental issues.</p>
            </div>
            <div class="vocab-item">
                <h3>cloth <button onclick="speak('cloth')">▶️ Hear</button></h3>
                <p><strong>Context:</strong> as stoffa (fabric)</p>
                <p><strong>Meaning:</strong> a type of fabric or material used for making clothes, curtains, etc.</p>
                <p><strong>Example:</strong> She bought a beautiful piece of cloth to make a dress.</p>
            </div>
        </div>

        <!-- Fill in the Gaps (Writing) Section -->
        <div id="writing" class="section">
            <h2>Fill in the Gaps (Writing)</h2>
            <div class="word-bank" id="wordBank">
                <div onclick="selectWord('unfortunately')">unfortunately</div>
                <div onclick="selectWord('capacity')">capacity</div>
                <div onclick="selectWord('awareness')">awareness</div>
                <div onclick="selectWord('cloth')">cloth</div>
            </div>
            <div class="sentence" id="sentence3">
                <p>The factory is operating at full <input type="text" id="input3" placeholder="___">.</p>
                <div class="feedback" id="feedback3"></div>
            </div>
            <div class="sentence" id="sentence1">
                <p><input type="text" id="input1" placeholder="___">, we couldn't attend the meeting.</p>
                <div class="feedback" id="feedback1"></div>
            </div>
            <div class="sentence" id="sentence4">
                <p>She wrapped the gift in a beautiful piece of <input type="text" id="input4" placeholder="___">.</p>
                <div class="feedback" id="feedback4"></div>
            </div>
            <div class="sentence" id="sentence2">
                <p>There is a growing <input type="text" id="input2" placeholder="___"> of mental health issues.</p>
                <div class="feedback" id="feedback2"></div>
            </div>
            <button onclick="checkWritingAnswers()">Check Answers</button>
            <button onclick="resetWriting()">Reset</button>
        </div>

        <!-- Match Definitions Section -->
        <div id="matching" class="section">
            <h2>Match Definitions</h2>
            <div class="match-container">
                <div class="match-column">
                    <h3>Words</h3>
                    <div class="match-item" onclick="selectWordMatch('unfortunately')">unfortunately</div>
                    <div class="match-item" onclick="selectWordMatch('capacity')">capacity</div>
                    <div class="match-item" onclick="selectWordMatch('awareness')">awareness</div>
                    <div class="match-item" onclick="selectWordMatch('cloth')">cloth</div>
                </div>
                <div class="match-column">
                    <h3>Definitions</h3>
                    <div class="match-item" onclick="selectDefinitionMatch('used to express sadness, regret, or disappointment about something')">used to express sadness, regret, or disappointment about something</div>
                    <div class="match-item" onclick="selectDefinitionMatch('the maximum amount that something can contain or produce')">the maximum amount that something can contain or produce</div>
                    <div class="match-item" onclick="selectDefinitionMatch('knowledge or understanding of a subject, issue, or situation')">knowledge or understanding of a subject, issue, or situation</div>
                    <div class="match-item" onclick="selectDefinitionMatch('a type of fabric or material used for making clothes, curtains, etc.')">a type of fabric or material used for making clothes, curtains, etc.</div>
                </div>
            </div>
            <button onclick="checkMatchingAnswers()">Check Matches</button>
            <button onclick="resetMatching()">Reset</button>
        </div>

        <!-- Fill in the Gaps (Pronunciation) Section -->
        <div id="pronunciation" class="section">
            <h2>Fill in the Gaps (Pronunciation)</h2>
            <div class="word-bank" id="pronunciationWordBank">
                <div>unfortunately</div>
                <div>capacity</div>
                <div>awareness</div>
                <div>cloth</div>
            </div>
            <div class="sentence">
                <p><span class="pronunciation-input"><input type="text" id="pronunciationInput1" placeholder="___" readonly> <button class="microphone-btn" onclick="startRecognition('unfortunately', 'pronunciationInput1')">🎤</button></span>, the train was delayed.</p>
                <div class="feedback" id="pronunciationFeedback1"></div>
            </div>
            <div class="sentence">
                <p>The stadium has a <span class="pronunciation-input"><input type="text" id="pronunciationInput2" placeholder="___" readonly> <button class="microphone-btn" onclick="startRecognition('capacity', 'pronunciationInput2')">🎤</button></span> of 80,000 people.</p>
                <div class="feedback" id="pronunciationFeedback2"></div>
            </div>
            <div class="sentence">
                <p>There is a growing <span class="pronunciation-input"><input type="text" id="pronunciationInput3" placeholder="___" readonly> <button class="microphone-btn" onclick="startRecognition('awareness', 'pronunciationInput3')">🎤</button></span> of climate change.</p>
                <div class="feedback" id="pronunciationFeedback3"></div>
            </div>
            <div class="sentence">
                <p>She bought a piece of <span class="pronunciation-input"><input type="text" id="pronunciationInput4" placeholder="___" readonly> <button class="microphone-btn" onclick="startRecognition('cloth', 'pronunciationInput4')">🎤</button></span> to make curtains.</p>
                <div class="feedback" id="pronunciationFeedback4"></div>
            </div>
        </div>
    </div>

    <script>
        let score = 0;
        const totalScore = 12;
        let selectedWord = null;
        let selectedDefinition = null;
        let selectedWordMatch = null;
        let selectedInput = null;
        let recognition = null;

        // Initialize speech recognition
        if ('webkitSpeechRecognition' in window) {
            recognition = new webkitSpeechRecognition();
        } else if ('SpeechRecognition' in window) {
            recognition = new SpeechRecognition();
        }

        if (recognition) {
            recognition.continuous = false;
            recognition.interimResults = false;
            recognition.lang = 'en-US';

            recognition.onresult = function(event) {
                const result = event.results[0][0].transcript.trim().toLowerCase();
                const expectedWord = selectedInput.dataset.expected.toLowerCase();
                const inputField = document.getElementById(selectedInput.id);

                if (result === expectedWord) {
                    inputField.value = selectedInput.dataset.expected;
                    inputField.className = 'correct';
                    document.getElementById('pronunciationFeedback' + selectedInput.id.slice(-1)).textContent = 'Correct!';
                    document.getElementById('pronunciationFeedback' + selectedInput.id.slice(-1)).style.color = 'green';
                    if (!selectedInput.dataset.scored) {
                        score++;
                        selectedInput.dataset.scored = 'true';
                        updateScore();
                    }
                } else {
                    inputField.className = 'incorrect';
                    document.getElementById('pronunciationFeedback' + selectedInput.id.slice(-1)).textContent = `Incorrect. You said: "${result}". Try again!`;
                    document.getElementById('pronunciationFeedback' + selectedInput.id.slice(-1)).style.color = 'red';
                }
            };

            recognition.onerror = function(event) {
                document.getElementById('pronunciationFeedback' + selectedInput.id.slice(-1)).textContent = 'Error occurred in recognition: ' + event.error;
                document.getElementById('pronunciationFeedback' + selectedInput.id.slice(-1)).style.color = 'red';
            };
        }

        function startRecognition(expectedWord, inputId) {
            selectedInput = document.getElementById(inputId);
            selectedInput.dataset.expected = expectedWord;
            if (recognition) {
                recognition.start();
            } else {
                alert('Speech recognition not supported in your browser.');
            }
        }

        function showSection(sectionId) {
            document.querySelectorAll('.section').forEach(section => {
                section.classList.remove('active');
            });
            document.getElementById(sectionId).classList.add('active');
        }

        function speak(word) {
            const u = new SpeechSynthesisUtterance(word);
            u.lang = "en-US";
            speechSynthesis.speak(u);
        }

        function selectWord(word) {
            selectedWord = word;
            document.querySelectorAll('#wordBank div').forEach(div => {
                div.style.backgroundColor = div.textContent === word ? '#a5d8ff' : 'rgba(255, 255, 255, 0.2)';
            });
        }

        function checkWritingAnswers() {
            // Check sentence 1
            const input1 = document.getElementById('input1').value.trim().toLowerCase();
            if (input1 === 'unfortunately') {
                document.getElementById('input1').className = 'correct';
                document.getElementById('feedback1').textContent = 'Correct!';
                document.getElementById('feedback1').style.color = 'green';
                if (!document.getElementById('input1').dataset.scored) {
                    score++;
                    document.getElementById('input1').dataset.scored = 'true';
                }
            } else {
                document.getElementById('input1').className = 'incorrect';
                document.getElementById('feedback1').textContent = 'Incorrect. Try again!';
                document.getElementById('feedback1').style.color = 'red';
            }

            // Check sentence 2
            const input2 = document.getElementById('input2').value.trim().toLowerCase();
            if (input2 === 'awareness') {
                document.getElementById('input2').className = 'correct';
                document.getElementById('feedback2').textContent = 'Correct!';
                document.getElementById('feedback2').style.color = 'green';
                if (!document.getElementById('input2').dataset.scored) {
                    score++;
                    document.getElementById('input2').dataset.scored = 'true';
                }
            } else {
                document.getElementById('input2').className = 'incorrect';
                document.getElementById('feedback2').textContent = 'Incorrect. Try again!';
                document.getElementById('feedback2').style.color = 'red';
            }

            // Check sentence 3
            const input3 = document.getElementById('input3').value.trim().toLowerCase();
            if (input3 === 'capacity') {
                document.getElementById('input3').className = 'correct';
                document.getElementById('feedback3').textContent = 'Correct!';
                document.getElementById('feedback3').style.color = 'green';
                if (!document.getElementById('input3').dataset.scored) {
                    score++;
                    document.getElementById('input3').dataset.scored = 'true';
                }
            } else {
                document.getElementById('input3').className = 'incorrect';
                document.getElementById('feedback3').textContent = 'Incorrect. Try again!';
                document.getElementById('feedback3').style.color = 'red';
            }

            // Check sentence 4
            const input4 = document.getElementById('input4').value.trim().toLowerCase();
            if (input4 === 'cloth') {
                document.getElementById('input4').className = 'correct';
                document.getElementById('feedback4').textContent = 'Correct!';
                document.getElementById('feedback4').style.color = 'green';
                if (!document.getElementById('input4').dataset.scored) {
                    score++;
                    document.getElementById('input4').dataset.scored = 'true';
                }
            } else {
                document.getElementById('input4').className = 'incorrect';
                document.getElementById('feedback4').textContent = 'Incorrect. Try again!';
                document.getElementById('feedback4').style.color = 'red';
            }

            updateScore();
        }

        function resetWriting() {
            document.querySelectorAll('#writing input[type="text"]').forEach(input => {
                input.value = '';
                input.className = '';
                input.dataset.scored = '';
            });
            document.querySelectorAll('#writing .feedback').forEach(feedback => {
                feedback.textContent = '';
            });
        }

        function selectWordMatch(word) {
            selectedWordMatch = word;
            document.querySelectorAll('.match-item').forEach(item => {
                if (item.textContent === word) {
                    item.classList.add('selected');
                } else {
                    item.classList.remove('selected');
                }
            });
        }

        function selectDefinitionMatch(definition) {
            if (selectedWordMatch) {
                const definitionElement = Array.from(document.querySelectorAll('.match-item')).find(el => el.textContent === definition);
                if (definitionElement) {
                    definitionElement.classList.add('selected');
                    checkMatch(selectedWordMatch, definition);
                }
            }
        }

        function checkMatch(word, definition) {
            const correctPairs = {
                'unfortunately': 'used to express sadness, regret, or disappointment about something',
                'capacity': 'the maximum amount that something can contain or produce',
                'awareness': 'knowledge or understanding of a subject, issue, or situation',
                'cloth': 'a type of fabric or material used for making clothes, curtains, etc.'
            };

            if (correctPairs[word] === definition) {
                document.querySelectorAll('.match-item').forEach(item => {
                    if (item.textContent === word || item.textContent === definition) {
                        item.classList.add('correct');
                        item.classList.remove('selected');
                    }
                });
                if (!document.querySelector(`.match-item:not(.correct):contains('${word}')`).dataset.scored) {
                    score++;
                    document.querySelector(`.match-item:not(.correct):contains('${word}')`).dataset.scored = 'true';
                    updateScore();
                }
            } else {
                alert('Incorrect match. Try again!');
            }
            selectedWordMatch = null;
        }

        function checkMatchingAnswers() {
            updateScore();
        }

        function resetMatching() {
            document.querySelectorAll('.match-item').forEach(item => {
                item.classList.remove('correct', 'selected');
                item.dataset.scored = '';
            });
        }

        function updateScore() {
            document.querySelector('.score').textContent = `Score: ${score} / ${totalScore}`;
        }
    </script>
</body>
</html>
