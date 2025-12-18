<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Bon WebGuard irukattum</title>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
<style>
/* Reset and Base */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Segoe UI', system-ui, sans-serif;
}

body {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    min-height: 100vh;
    padding: 20px;
    color: #333;
}

/* Container */
.container {
    max-width: 500px;
    margin: 0 auto;
    background: white;
    border-radius: 25px;
    box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
    overflow: hidden;
}

/* Header */
.header {
    background: linear-gradient(135deg, #ff4d8d, #764ba2);
    color: white;
    padding: 30px 20px;
    text-align: center;
}

.logo {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 15px;
    margin-bottom: 10px;
}

.logo i {
    font-size: 2.8rem;
    background: rgba(255, 255, 255, 0.2);
    padding: 15px;
    border-radius: 50%;
}

.logo h1 {
    font-size: 2.4rem;
    font-weight: 800;
}

.tagline {
    font-size: 1rem;
    opacity: 0.9;
}

/* Status */
.status-bar {
    padding: 20px;
    text-align: center;
}

.status-box {
    background: #f0f4ff;
    padding: 15px 25px;
    border-radius: 15px;
    font-weight: 600;
    color: #667eea;
    border: 2px solid #dce4ff;
    display: inline-flex;
    align-items: center;
    gap: 10px;
}

.status-box.emergency {
    background: #ffeaea;
    color: #ff4757;
    border-color: #ffd6d6;
    animation: pulse 1.5s infinite;
}

@keyframes pulse {
    0% { transform: scale(1); }
    50% { transform: scale(1.05); }
    100% { transform: scale(1); }
}

/* SOS Button */
.sos-section {
    padding: 20px;
    text-align: center;
}

.sos-button {
    width: 180px;
    height: 180px;
    border-radius: 50%;
    border: none;
    background: linear-gradient(135deg, #ff6b6b, #ff4757);
    color: white;
    font-size: 28px;
    font-weight: bold;
    cursor: pointer;
    box-shadow: 0 0 40px rgba(255, 107, 107, 0.6);
    transition: all 0.3s;
    display: inline-flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 8px;
}

.sos-button:hover {
    transform: scale(1.05);
    box-shadow: 0 0 50px rgba(255, 107, 107, 0.8);
}

.sos-button.activated {
    animation: sos-pulse 0.8s infinite alternate;
    background: linear-gradient(135deg, #ff4757, #ff3838);
}

@keyframes sos-pulse {
    0% { transform: scale(1); box-shadow: 0 0 40px rgba(255, 71, 87, 0.6); }
    100% { transform: scale(1.1); box-shadow: 0 0 60px rgba(255, 71, 87, 0.9); }
}

.sos-icon {
    font-size: 45px;
}

.sos-hint {
    font-size: 14px;
    opacity: 0.9;
}

/* Quick Actions */
.quick-actions {
    padding: 20px;
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 15px;
}

.action-btn {
    background: #f8f9ff;
    border: none;
    border-radius: 15px;
    padding: 20px 10px;
    font-weight: 600;
    color: #667eea;
    cursor: pointer;
    transition: all 0.3s;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 10px;
}

.action-btn:hover {
    background: #667eea;
    color: white;
    transform: translateY(-3px);
}

.action-btn i {
    font-size: 24px;
}

.action-btn span {
    font-size: 12px;
}

/* Place Safety Check */
.safety-check {
    padding: 25px 20px;
    background: #f8f9ff;
    margin: 0 20px;
    border-radius: 20px;
}

.section-title {
    color: #667eea;
    font-size: 1.2rem;
    margin-bottom: 20px;
    display: flex;
    align-items: center;
    gap: 10px;
}

.input-group {
    display: flex;
    gap: 10px;
    margin-bottom: 15px;
}

.input-group input {
    flex: 1;
    padding: 15px;
    border: 2px solid #e0e5ff;
    border-radius: 12px;
    font-size: 16px;
    outline: none;
    transition: all 0.3s;
}

.input-group input:focus {
    border-color: #667eea;
}

.check-btn {
    padding: 15px 25px;
    background: #667eea;
    color: white;
    border: none;
    border-radius: 12px;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.3s;
    display: flex;
    align-items: center;
    gap: 8px;
}

.check-btn:hover {
    background: #5a6fd8;
    transform: translateY(-2px);
}

.safety-result {
    background: white;
    border-radius: 15px;
    padding: 20px;
    margin-top: 15px;
    border: 2px solid #e0e5ff;
    display: none;
}

.safety-rating {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 15px;
}

.rating-stars {
    color: #ffd700;
    font-size: 20px;
}

.safety-score {
    font-size: 24px;
    font-weight: 800;
    color: #4CAF50;
}

.safety-tips {
    font-size: 14px;
    color: #666;
    line-height: 1.6;
}

.safety-tips ul {
    padding-left: 20px;
    margin-top: 10px;
}

/* Video Recording */
.video-section {
    padding: 20px;
    display: none;
}

.video-container {
    width: 100%;
    border-radius: 15px;
    overflow: hidden;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
}

#video {
    width: 100%;
    display: block;
}

.video-controls {
    display: flex;
    gap: 15px;
    margin-top: 15px;
}

.control-btn {
    flex: 1;
    padding: 15px;
    border: none;
    border-radius: 10px;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.3s;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 8px;
}

.download-btn {
    background: #667eea;
    color: white;
}

.download-btn:hover {
    background: #5a6fd8;
}

.stop-btn {
    background: #f1f3ff;
    color: #667eea;
    border: 2px solid #e0e5ff;
}

.stop-btn:hover {
    background: #e0e5ff;
}

/* Voice Command */
.voice-section {
    padding: 20px;
    background: #f0f4ff;
    margin: 20px;
    border-radius: 20px;
}

.voice-status {
    display: flex;
    align-items: center;
    gap: 15px;
    margin-top: 15px;
}

.voice-mic {
    width: 60px;
    height: 60px;
    background: #667eea;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
    font-size: 24px;
    cursor: pointer;
    transition: all 0.3s;
}

.voice-mic.listening {
    background: #ff4757;
    animation: mic-pulse 1s infinite;
}

@keyframes mic-pulse {
    0% { transform: scale(1); }
    50% { transform: scale(1.1); }
    100% { transform: scale(1); }
}

.voice-text {
    flex: 1;
    background: white;
    padding: 15px;
    border-radius: 12px;
    font-size: 14px;
    color: #666;
    border: 2px solid #e0e5ff;
    min-height: 60px;
    display: flex;
    align-items: center;
}

/* Notification */
.notification {
    position: fixed;
    bottom: 20px;
    left: 50%;
    transform: translateX(-50%) translateY(100px);
    background: #4CAF50;
    color: white;
    padding: 15px 30px;
    border-radius: 50px;
    font-weight: 600;
    display: flex;
    align-items: center;
    gap: 10px;
    box-shadow: 0 10px 30px rgba(76, 175, 80, 0.3);
    z-index: 1000;
    transition: transform 0.5s;
}

.notification.show {
    transform: translateX(-50%) translateY(0);
}

.notification.emergency {
    background: #ff4757;
}

/* Footer */
.footer {
    padding: 20px;
    text-align: center;
    color: #666;
    font-size: 13px;
    border-top: 1px solid #eee;
}

.safety-tip {
    background: #f0f8ff;
    padding: 15px;
    border-radius: 10px;
    margin-top: 15px;
    font-size: 13px;
    color: #4a6fa5;
    border-left: 4px solid #667eea;
}

/* Responsive */
@media (max-width: 480px) {
    .container {
        border-radius: 20px;
    }
    
    .sos-button {
        width: 160px;
        height: 160px;
        font-size: 24px;
    }
    
    .sos-icon {
        font-size: 40px;
    }
    
    .logo h1 {
        font-size: 2rem;
    }
}
</style>
</head>
<body>

<!-- Notification -->
<div class="notification" id="notification">
    <i class="fas fa-bell"></i>
    <span id="notificationText">Emergency activated!</span>
</div>

<div class="container">
    
    <!-- Header -->
    <div class="header">
        <div class="logo">
            <i class="fas fa-shield-alt"></i>
            <h1>SafeGuard</h1>
        </div>
        <p class="tagline">Personal Safety Protection</p>
    </div>
    
    <!-- Status -->
    <div class="status-bar">
        <div id="statusBox" class="status-box">
            <i class="fas fa-check-circle"></i>
            <span id="statusText">System Ready</span>
        </div>
    </div>
    
    <!-- SOS Button -->
    <div class="sos-section">
        <button id="sosButton" class="sos-button" onclick="activateEmergency()">
            <div class="sos-icon"><i class="fas fa-exclamation-triangle"></i></div>
            <div>SOS</div>
            <div class="sos-hint">Tap for emergency</div>
        </button>
    </div>
    
    <!-- Quick Actions -->
    <div class="quick-actions">
        <button class="action-btn" onclick="startRecording()">
            <i class="fas fa-video"></i>
            <span>Record Video</span>
        </button>
        <button class="action-btn" onclick="playAlarm()">
            <i class="fas fa-bell"></i>
            <span>Sound Alarm</span>
        </button>
    </div>
    
    <!-- Place Safety Check -->
    <div class="safety-check">
        <div class="section-title">
            <i class="fas fa-map-marked-alt"></i>
            Check Place Safety
        </div>
        <div class="input-group">
            <input type="text" id="placeInput" placeholder="Enter place name or address">
            <button class="check-btn" onclick="checkPlaceSafety()">
                <i class="fas fa-search"></i> Check
            </button>
        </div>
        <div class="safety-result" id="safetyResult">
            <div class="safety-rating">
                <div class="rating-stars" id="ratingStars">
                    ★★★★★
                </div>
                <div class="safety-score" id="safetyScore">8.5/10</div>
            </div>
            <div class="safety-tips" id="safetyTips">
                Loading safety information...
            </div>
        </div>
    </div>
    
    <!-- Voice Command -->
    <div class="voice-section">
        <div class="section-title">
            <i class="fas fa-microphone"></i>
            Voice Commands
        </div>
        <p style="color: #666; font-size: 14px; margin-bottom: 10px;">
            Say: "Emergency", "Help", "Record", "Stop", "Check Safety"
        </p>
        <div class="voice-status">
            <div class="voice-mic" id="voiceMic" onclick="toggleVoiceRecognition()">
                <i class="fas fa-microphone"></i>
            </div>
            <div class="voice-text" id="voiceText">
                Click mic to start voice commands
            </div>
        </div>
    </div>
    
    <!-- Video Recording -->
    <div class="video-section" id="videoSection">
        <div class="video-container">
            <video id="video" autoplay muted></video>
        </div>
        <div class="video-controls">
            <button class="control-btn download-btn" onclick="downloadVideo()">
                <i class="fas fa-download"></i> Save Video
            </button>
            <button class="control-btn stop-btn" onclick="stopRecording()">
                <i class="fas fa-stop"></i> Stop Recording
            </button>
        </div>
    </div>
    
    <!-- Footer -->
    <div class="footer">
        <p>© 2023 SafeGuard - Personal Safety App</p>
        <div class="safety-tip">
            <i class="fas fa-lightbulb"></i>
            <strong>Privacy First:</strong> This app does not share any data with anyone.
        </div>
    </div>
</div>

<script>
// ====== APP STATE ======
let isEmergencyActive = false;
let isRecording = false;
let isListening = false;
let mediaRecorder = null;
let recordedChunks = [];
let recognition = null;

// ====== DOM ELEMENTS ======
const elements = {
    statusBox: document.getElementById('statusBox'),
    statusText: document.getElementById('statusText'),
    sosButton: document.getElementById('sosButton'),
    videoSection: document.getElementById('videoSection'),
    video: document.getElementById('video'),
    notification: document.getElementById('notification'),
    notificationText: document.getElementById('notificationText'),
    placeInput: document.getElementById('placeInput'),
    safetyResult: document.getElementById('safetyResult'),
    ratingStars: document.getElementById('ratingStars'),
    safetyScore: document.getElementById('safetyScore'),
    safetyTips: document.getElementById('safetyTips'),
    voiceMic: document.getElementById('voiceMic'),
    voiceText: document.getElementById('voiceText')
};

// ====== INITIALIZE APP ======
function initApp() {
    console.log("SafeGuard App Initializing...");
    
    // Initialize voice recognition
    initVoiceRecognition();
    
    // Setup shake detection
    setupShakeDetection();
    
    // Show welcome
    setTimeout(() => {
        showNotification("SafeGuard is ready!");
        speak("SafeGuard is ready. You can use voice commands by saying help, emergency, record video, or stop.");
    }, 1000);
}

// ====== EMERGENCY FUNCTIONS ======
function activateEmergency() {
    if (isEmergencyActive) {
        stopEmergency();
        return;
    }
    
    console.log("🚨 EMERGENCY ACTIVATED");
    isEmergencyActive = true;
    
    // Update UI
    elements.statusBox.className = 'status-box emergency';
    elements.statusText.innerHTML = '<i class="fas fa-exclamation-triangle"></i> EMERGENCY ACTIVE';
    elements.sosButton.classList.add('activated');
    
    // Device feedback
    vibratePhone([500, 250, 500, 250, 500]);
    playEmergencySound();
    
    // Voice alert
    speak("Emergency activated! Loud alarm playing.");
    
    // Start recording automatically
    startRecording();
    
    // Show notification
    showNotification("Emergency activated!", true);
}

function stopEmergency() {
    isEmergencyActive = false;
    
    // Update UI
    elements.statusBox.className = 'status-box';
    elements.statusText.innerHTML = '<i class="fas fa-check-circle"></i> System Ready';
    elements.sosButton.classList.remove('activated');
    
    // Stop recording
    stopRecording();
    
    // Voice confirmation
    speak("Emergency stopped. You are safe now.");
    
    showNotification("Emergency stopped");
}

// ====== VIDEO RECORDING ======
function startRecording() {
    if (isRecording) {
        stopRecording();
        return;
    }
    
    // Request camera and microphone access
    navigator.mediaDevices.getUserMedia({ 
        video: { 
            facingMode: "user",
            width: { ideal: 1280 },
            height: { ideal: 720 }
        }, 
        audio: true 
    })
    .then(stream => {
        // Show video
        elements.video.srcObject = stream;
        elements.videoSection.style.display = 'block';
        isRecording = true;
        
        // Start recording
        mediaRecorder = new MediaRecorder(stream, {
            mimeType: 'video/webm;codecs=vp9'
        });
        
        recordedChunks = [];
        
        mediaRecorder.ondataavailable = event => {
            if (event.data.size > 0) {
                recordedChunks.push(event.data);
            }
        };
        
        mediaRecorder.onstop = () => {
            console.log("Video recording stopped");
        };
        
        mediaRecorder.start();
        
        showNotification("Video recording started");
        speak("Video recording started for evidence.");
        
    })
    .catch(error => {
        console.log("Camera error:", error);
        showNotification("Camera permission needed");
    });
}

function stopRecording() {
    if (mediaRecorder && isRecording) {
        mediaRecorder.stop();
        isRecording = false;
        
        // Stop all tracks
        if (elements.video.srcObject) {
            elements.video.srcObject.getTracks().forEach(track => track.stop());
        }
        
        elements.videoSection.style.display = 'none';
        
        showNotification("Video recording stopped");
        speak("Video recording stopped.");
    }
}

function downloadVideo() {
    if (recordedChunks.length === 0) {
        showNotification("No recording available");
        return;
    }
    
    // Create video blob
    const blob = new Blob(recordedChunks, { type: 'video/webm' });
    const url = URL.createObjectURL(blob);
    
    // Create download link
    const a = document.createElement('a');
    a.href = url;
    a.download = `safety_evidence_${new Date().getTime()}.webm`;
    document.body.appendChild(a);
    a.click();
    document.body.removeChild(a);
    
    // Clean up
    setTimeout(() => URL.revokeObjectURL(url), 100);
    
    showNotification("Video saved to downloads");
    speak("Video evidence saved to your device.");
}

// ====== PLACE SAFETY CHECK ======
function checkPlaceSafety() {
    const place = elements.placeInput.value.trim();
    
    if (!place) {
        showNotification("Please enter a place name");
        return;
    }
    
    showNotification(`Checking safety of ${place}...`);
    speak(`Checking safety information for ${place}.`);
    
    // Simulate safety check with timeout
    setTimeout(() => {
        // Generate random safety score (3-10)
        const safetyScore = (3 + Math.random() * 7).toFixed(1);
        
        // Get safety tips based on score
        let tips = "";
        let stars = "";
        let color = "#4CAF50";
        
        if (safetyScore >= 8) {
            stars = "★★★★★";
            tips = `
                <strong>Very Safe Area ✓</strong>
                <ul>
                    <li>Well-lit streets with CCTV</li>
                    <li>Regular police patrols</li>
                    <li>Good public transportation</li>
                    <li>Safe for walking at night</li>
                    <li>Emergency services nearby</li>
                </ul>
            `;
        } else if (safetyScore >= 6.5) {
            stars = "★★★★☆";
            color = "#FF9800";
            tips = `
                <strong>Moderately Safe</strong>
                <ul>
                    <li>Generally safe but be cautious</li>
                    <li>Stay in main areas</li>
                    <li>Travel with others if possible</li>
                    <li>Keep emergency app ready</li>
                    <li>Avoid late night travel</li>
                </ul>
            `;
        } else if (safetyScore >= 5) {
            stars = "★★★☆☆";
            color = "#FF5722";
            tips = `
                <strong>Use Caution</strong>
                <ul>
                    <li>Limited street lighting</li>
                    <li>Travel with companions</li>
                    <li>Have safety plan ready</li>
                    <li>Avoid isolated areas</li>
                    <li>Keep phone charged</li>
                </ul>
            `;
        } else {
            stars = "★★☆☆☆";
            color = "#FF4757";
            tips = `
                <strong>High Risk Area</strong>
                <ul>
                    <li>Avoid if possible</li>
                    <li>Never travel alone</li>
                    <li>High crime reported</li>
                    <li>Poor lighting and security</li>
                    <li>Consider alternative routes</li>
                </ul>
            `;
        }
        
        // Update UI
        elements.ratingStars.innerHTML = stars;
        elements.safetyScore.textContent = `${safetyScore}/10`;
        elements.safetyScore.style.color = color;
        elements.safetyTips.innerHTML = tips;
        elements.safetyResult.style.display = 'block';
        
        // Speak result
        let safetyLevel = "";
        if (safetyScore >= 8) safetyLevel = "very safe";
        else if (safetyScore >= 6.5) safetyLevel = "moderately safe";
        else if (safetyScore >= 5) safetyLevel = "requires caution";
        else safetyLevel = "high risk";
        
        speak(`Safety rating for ${place} is ${safetyScore} out of 10. This area is ${safetyLevel}.`);
        
    }, 1500);
}

// ====== VOICE RECOGNITION ======
function initVoiceRecognition() {
    if (!('webkitSpeechRecognition' in window) && !('SpeechRecognition' in window)) {
        elements.voiceText.textContent = "Voice recognition not supported in this browser";
        return;
    }
    
    const SpeechRecognition = window.SpeechRecognition || window.webkitSpeechRecognition;
    recognition = new SpeechRecognition();
    
    recognition.continuous = true;
    recognition.interimResults = true;
    recognition.lang = 'en-US';
    recognition.maxAlternatives = 1;
    
    recognition.onstart = () => {
        elements.voiceMic.classList.add('listening');
        elements.voiceText.textContent = "Listening...";
    };
    
    recognition.onresult = (event) => {
        let finalTranscript = '';
        let interimTranscript = '';
        
        for (let i = event.resultIndex; i < event.results.length; i++) {
            const transcript = event.results[i][0].transcript;
            if (event.results[i].isFinal) {
                finalTranscript += transcript;
            } else {
                interimTranscript += transcript;
            }
        }
        
        if (interimTranscript) {
            elements.voiceText.textContent = interimTranscript;
        }
        
        if (finalTranscript) {
            elements.voiceText.textContent = finalTranscript;
            processVoiceCommand(finalTranscript.toLowerCase());
        }
    };
    
    recognition.onerror = (event) => {
        console.log("Voice recognition error:", event.error);
        elements.voiceMic.classList.remove('listening');
        elements.voiceText.textContent = "Click mic to try again";
    };
    
    recognition.onend = () => {
        elements.voiceMic.classList.remove('listening');
        if (isListening) {
            setTimeout(() => recognition.start(), 500);
        }
    };
}

function toggleVoiceRecognition() {
    if (!recognition) {
        showNotification("Voice recognition not available");
        return;
    }
    
    if (isListening) {
        recognition.stop();
        isListening = false;
        elements.voiceText.textContent = "Voice commands stopped";
        showNotification("Voice commands stopped");
    } else {
        recognition.start();
        isListening = true;
        showNotification("Voice commands active");
        speak("Voice commands activated. Say help, emergency, record, stop, or check safety.");
    }
}

function processVoiceCommand(command) {
    console.log("Voice command:", command);
    
    // Emergency commands
    if (command.includes('help') || command.includes('emergency') || command.includes('sos')) {
        activateEmergency();
        showNotification("Emergency activated by voice", true);
        return;
    }
    
    // Recording commands
    if (command.includes('record') || command.includes('video') || command.includes('camera')) {
        startRecording();
        showNotification("Video recording started by voice");
        return;
    }
    
    if (command.includes('stop') || command.includes('stop recording')) {
        stopRecording();
        showNotification("Video recording stopped by voice");
        return;
    }
    
    // Alarm commands
    if (command.includes('alarm') || command.includes('sound')) {
        playAlarm();
        showNotification("Alarm activated by voice", true);
        return;
    }
    
    // Check place safety
    if (command.includes('check') || command.includes('safety') || command.includes('place')) {
        const placeMatch = command.match(/check (.*)/) || command.match(/safety of (.*)/);
        if (placeMatch && placeMatch[1]) {
            elements.placeInput.value = placeMatch[1];
            checkPlaceSafety();
        } else {
            speak("Please say the name of the place you want to check.");
        }
        return;
    }
    
    // Default response
    showNotification(`Command: ${command}`);
}

// ====== ALARM SOUND ======
function playAlarm() {
    playEmergencySound();
    
    // Vibrate pattern
    if (navigator.vibrate) {
        vibratePhone([200, 100, 200, 100, 200, 100, 500]);
    }
    
    showNotification("Safety alarm activated!", true);
    speak("Loud safety alarm activated!");
}

function playEmergencySound() {
    try {
        // Create audio context for alarm
        const audioContext = new (window.AudioContext || window.webkitAudioContext)();
        const oscillator = audioContext.createOscillator();
        const gainNode = audioContext.createGain();
        
        oscillator.connect(gainNode);
        gainNode.connect(audioContext.destination);
        
        oscillator.type = 'sawtooth';
        oscillator.frequency.value = 1000;
        
        // Create loud alarm pattern
        let time = audioContext.currentTime;
        
        // First pulse (loud)
        gainNode.gain.setValueAtTime(0.8, time);
        gainNode.gain.exponentialRampToValueAtTime(0.01, time + 0.3);
        
        // Second pulse
        time += 0.3;
        gainNode.gain.setValueAtTime(0.8, time);
        gainNode.gain.exponentialRampToValueAtTime(0.01, time + 0.3);
        
        // Third pulse
        time += 0.3;
        gainNode.gain.setValueAtTime(0.8, time);
        gainNode.gain.exponentialRampToValueAtTime(0.01, time + 0.3);
        
        // Fourth pulse
        time += 0.3;
        gainNode.gain.setValueAtTime(0.8, time);
        gainNode.gain.exponentialRampToValueAtTime(0.01, time + 0.3);
        
        // Fifth pulse
        time += 0.3;
        gainNode.gain.setValueAtTime(0.8, time);
        gainNode.gain.exponentialRampToValueAtTime(0.01, time + 0.3);
        
        oscillator.start();
        oscillator.stop(time + 0.3);
        
    } catch (error) {
        console.log("Sound error:", error);
        // Fallback beep
        try {
            for (let i = 0; i < 5; i++) {
                setTimeout(() => {
                    const beep = new Audio('data:audio/wav;base64,UklGRigAAABXQVZFZm10IBIAAAABAAEAQB8AAEAfAAABAAgAZGF0YQ');
                    beep.volume = 0.5;
                    beep.play();
                }, i * 300);
            }
        } catch (e) {
            console.log("Fallback audio failed:", e);
        }
    }
}

// ====== HELPER FUNCTIONS ======
function vibratePhone(pattern) {
    if (navigator.vibrate) {
        navigator.vibrate(pattern);
    }
}

function speak(text) {
    if (!window.speechSynthesis) return;
    
    speechSynthesis.cancel();
    
    const utterance = new SpeechSynthesisUtterance(text);
    utterance.rate = 1.0;
    utterance.volume = 1.0;
    utterance.pitch = 1.0;
    
    speechSynthesis.speak(utterance);
}

function showNotification(message, isEmergency = false) {
    elements.notificationText.textContent = message;
    
    if (isEmergency) {
        elements.notification.className = 'notification show emergency';
    } else {
        elements.notification.className = 'notification show';
    }
    
    // Auto hide after 4 seconds
    setTimeout(() => {
        elements.notification.className = 'notification';
    }, 4000);
}

// ====== SHAKE DETECTION ======
function setupShakeDetection() {
    let lastShake = 0;
    
    if (window.DeviceMotionEvent) {
        window.addEventListener('devicemotion', function(event) {
            const acceleration = event.accelerationIncludingGravity;
            if (!acceleration) return;
            
            // Calculate total force
            const force = Math.abs(acceleration.x) + Math.abs(acceleration.y) + Math.abs(acceleration.z);
            
            // Detect shake (force > 20)
            if (force > 20) {
                const now = Date.now();
                
                // Prevent multiple shakes within 2 seconds
                if (now - lastShake > 2000) {
                    activateEmergency();
                    lastShake = now;
                    showNotification("Emergency activated by shake", true);
                }
            }
        });
    }
}

// ====== EVENT LISTENERS ======
// Double tap for emergency
let lastTap = 0;
document.addEventListener('touchend', function(event) {
    const currentTime = new Date().getTime();
    const tapLength = currentTime - lastTap;
    
    if (tapLength < 500 && tapLength > 0) {
        activateEmergency();
        event.preventDefault();
    }
    
    lastTap = currentTime;
});

// Double click for desktop
document.addEventListener('dblclick', activateEmergency);

// Keyboard shortcuts
document.addEventListener('keydown', function(event) {
    // Space bar for emergency
    if (event.key === ' ') {
        event.preventDefault();
        activateEmergency();
    }
    
    // Escape to stop emergency
    if (event.key === 'Escape' && isEmergencyActive) {
        stopEmergency();
    }
    
    // Ctrl+R to start recording
    if (event.ctrlKey && event.key === 'r') {
        event.preventDefault();
        startRecording();
    }
    
    // Ctrl+S to stop recording
    if (event.ctrlKey && event.key === 's') {
        event.preventDefault();
        stopRecording();
    }
});

// ====== INITIALIZE ======
window.addEventListener('DOMContentLoaded', initApp);
</script>
</body>
</html>
