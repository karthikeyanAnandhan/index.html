<style>
    /* CSS: டிசைன் பகுதிகள் */
    body {
        font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        margin: 0;
    }

    .card {
        background: white;
        padding: 30px;
        border-radius: 20px;
        box-shadow: 0 10px 25px rgba(0,0,0,0.2);
        text-align: center;
        width: 90%;
        max-width: 400px;
    }

    h1 { color: #e67e22; margin-bottom: 10px; }
    p { color: #7f8c8d; margin-bottom: 25px; }

    .input-group {
        display: flex;
        flex-direction: column;
        gap: 15px;
    }

    input {
        padding: 12px;
        border: 2px solid #ddd;
        border-radius: 10px;
        font-size: 16px;
        outline: none;
        transition: 0.3s;
    }

    input:focus { border-color: #e67e22; }

    button {
        padding: 12px;
        background-color: #e67e22;
        color: white;
        border: none;
        border-radius: 10px;
        font-size: 16px;
        font-weight: bold;
        cursor: pointer;
        transition: 0.3s;
    }

    button:hover { background-color: #d35400; transform: scale(1.02); }

    #result {
        margin-top: 25px;
        padding: 15px;
        border-radius: 10px;
        font-weight: bold;
        display: none; /* ஆரம்பத்தில் மறைத்து வைக்கப்படும் */
    }

    .available { background-color: #d4edda; color: #155724; display: block !important; }
    .not-available { background-color: #f8d7da; color: #721c24; display: block !important; }
</style>
<div class="card">
    <h1>சுவை உணவகம் 🍲</h1>
    <p>உங்களுக்கு வேண்டிய உணவு இருக்கிறதா?</p>
    
    <div class="input-group">
        <input type="text" id="foodSearch" placeholder="உதாரணம்: Biryani, Dosa...">
        <button onclick="checkAvailability()">தேடுக (Search)</button>
    </div>

    <div id="result"></div>
</div>

<script>
    // JavaScript: உணவுகளை சரிபார்க்கும் பகுதி
    
    // உங்கள் ஹோட்டல் மெனு பட்டியல் (இங்கே நீங்கள் உணவுகளைச் சேர்க்கலாம்)
    const hotelMenu = [
        "Biryani", "Chicken Rice", "Dosa", "Idli", 
        "Parotta", "Pongal", "Omelette", "Meals", "Chapati"
    ];

    function checkAvailability() {
        const userInput = document.getElementById("foodSearch").value.trim();
        const resultBox = document.getElementById("result");

        if (userInput === "") {
            alert("தயவுசெய்து ஏதாவது ஒரு உணவின் பெயரை உள்ளிடவும்!");
            return;
        }

        // மெனுவில் இருக்கிறதா என தேடுதல் (பெரிய/சிறிய எழுத்து வித்தியாசம் இன்றி)
        const found = hotelMenu.find(item => item.toLowerCase() === userInput.toLowerCase());

        if (found) {
            resultBox.innerHTML = `✅ மகிழ்ச்சி! <b>${found}</b> எங்களிடம் தயாராக உள்ளது.`;
            resultBox.className = "available";
        } else {
            resultBox.innerHTML = `❌ மன்னிக்கவும்! <b>${userInput}</b> தற்போது எங்களிடம் இல்லை.`;
            resultBox.className = "not-available";
        }
    }
</script>