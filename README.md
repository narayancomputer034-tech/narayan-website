<!DOCTYPE html>
<html lang="hi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Prince Look - Official Store</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        .gold-border { border: 2px solid #ffd700; box-shadow: 0 0 10px rgba(255, 215, 0, 0.3); }
        .bg-dark { background-color: #0a0a0a; }
    </style>
</head>
<body class="bg-dark text-white font-sans">
    <header class="p-6 text-center border-b border-yellow-600 bg-black">
        <h1 class="text-3xl font-bold text-yellow-500 tracking-tighter">PRINCE LOOK</h1>
        <p class="text-xs text-gray-400 mt-1">BIHAR TO BHARAT 🇮🇳</p>
    </header>

    <div class="container mx-auto p-4 max-w-4xl">
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8 mt-8">
            <div class="bg-gray-900 p-4 rounded-2xl gold-border text-center">
                <img src="https://via.placeholder.com/300" class="w-full rounded-xl mb-4" alt="Product">
                <h3 class="text-xl font-bold">Premium Logo T-Shirt</h3>
                <p class="text-yellow-500 text-2xl font-bold mt-2">₹499</p>
                <button onclick="openOrderForm('Premium Logo T-Shirt', '499')" class="mt-4 bg-yellow-500 text-black font-bold py-3 px-8 rounded-full hover:bg-yellow-400 transition w-full">अभी खरीदें</button>
            </div>
        </div>
    </div>

    <div id="orderModal" class="fixed inset-0 bg-black bg-opacity-90 hidden flex items-center justify-center p-4">
        <div class="bg-gray-800 p-6 rounded-2xl w-full max-w-md gold-border">
            <h2 class="text-xl font-bold text-yellow-500 mb-4">ऑर्डर की जानकारी भरें</h2>
            <input type="text" id="custName" placeholder="आपका नाम" class="w-full p-3 mb-3 bg-gray-700 rounded text-white border-none">
            <input type="text" id="custAddress" placeholder="पूरा पता (गाँव/शहर, जिला, पिनकोड)" class="w-full p-3 mb-3 bg-gray-700 rounded text-white border-none">
            <p id="selectedItem" class="text-sm text-gray-400 mb-4"></p>
            <button onclick="sendWhatsApp()" class="w-full bg-green-600 text-white font-bold py-3 rounded-lg">WhatsApp पर कन्फर्म करें</button>
            <button onclick="closeModal()" class="w-full mt-2 text-gray-400 text-sm">कैंसिल करें</button>
        </div>
    </div>

    <script>
        let currentItem = "";
        let currentPrice = "";

        function openOrderForm(name, price) {
            currentItem = name;
            currentPrice = price;
            document.getElementById('selectedItem').innerText = "प्रोडक्ट: " + name + " | कीमत: ₹" + price;
            document.getElementById('orderModal').classList.remove('hidden');
        }

        function closeModal() {
            document.getElementById('orderModal').classList.add('hidden');
        }

        function sendWhatsApp() {
            const name = document.getElementById('custName').value;
            const address = document.getElementById('custAddress').value;
            const phone = "916204187686";

            if(name === "" || address === "") {
                alert("कृपया नाम और पता भरें!");
                return;
            }

            const message = `*नया ऑर्डर - PRINCE LOOK*%0A--------------------------%0A*नाम:* ${name}%0A*पता:* ${address}%0A*प्रोडक्ट:* ${currentItem}%0A*कीमत:* ₹${currentPrice}%0A--------------------------%0Aकृपया ऑर्डर कन्फर्म करें।`;
            window.open(`https://wa.me/${phone}?text=${message}`, '_blank');
        }
    </script>
</body>
</html>
