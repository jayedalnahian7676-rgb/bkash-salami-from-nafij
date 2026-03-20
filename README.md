<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>bKash Salami - Nafij</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        body { background-color: #f5f5f5; font-family: 'Segoe UI', sans-serif; }
        .bkash-pink { background-color: #D12053; }
        .text-bkash { color: #D12053; }
        .app-screen { display: none; min-height: 100vh; width: 100%; max-width: 450px; margin: 0 auto; background: white; overflow: hidden; }
        .active { display: block; }
        .numpad-btn { background: #fdfdfd; border: 1px solid #f0f0f0; border-radius: 8px; height: 60px; font-size: 1.5rem; font-weight: 600; }
        .grid-icon { width: 50px; height: 50px; border-radius: 50%; display: flex; align-items: center; justify-content: center; margin: 0 auto 5px; background: white; border: 1px solid #eee; }
        .pin-dot { width: 12px; height: 12px; border-radius: 50%; border: 1px solid #ccc; transition: 0.2s; }
        .pin-dot.filled { background-color: #D12053; border-color: #D12053; }
    </style>
</head>
<body>

    <div id="screen-home" class="app-screen active">
        <div class="bkash-pink p-4 flex justify-between items-center text-white">
            <div class="flex items-center gap-3">
                <img src="https://i.ibb.co.com/rfwXpYjH/nafij.jpg" class="w-10 h-10 rounded-full border-2 border-white object-cover">
                <div>
                    <p class="text-[10px] opacity-90 uppercase">As-salamu Alaykum</p>
                    <p class="font-bold text-lg">NAFIJ</p>
                </div>
            </div>
            <img src="https://www.logo.wine/a/logo/BKash/BKash-Icon-Logo.wine.svg" class="w-10 brightness-200">
        </div>
        <div class="bkash-pink px-4 pb-6">
            <div class="bg-white rounded-full py-2 px-4 flex justify-between items-center w-44">
                <span class="text-bkash font-bold text-sm">৳ ৪,৯২,৮০,২২১</span>
                <i class="fa-solid fa-eye text-gray-200 text-xs"></i>
            </div>
        </div>
        <div class="grid grid-cols-4 gap-4 p-4 text-[10px] text-center font-medium text-gray-600">
            <div onclick="showScreen('screen-setup')" class="cursor-pointer">
                <div class="grid-icon text-pink-500"><i class="fa-solid fa-paper-plane text-xl"></i></div>সালামি পাঠান
            </div>
            <div><div class="grid-icon text-blue-500"><i class="fa-solid fa-mobile-screen text-xl"></i></div>রিচার্জ</div>
            <div><div class="grid-icon text-orange-500"><i class="fa-solid fa-gift text-xl"></i></div>অফার</div>
            <div><div class="grid-icon text-gray-400"><i class="fa-solid fa-ellipsis text-xl"></i></div>আরো</div>
        </div>
        <div class="mx-4 p-4 bg-pink-50 rounded-lg border border-pink-100 flex items-center gap-3">
            <i class="fa-solid fa-moon text-yellow-500 text-xl"></i>
            <p class="text-[11px] text-pink-900 font-semibold">ঈদ মোবারক! সালামি পাঠাতে উপরের আইকনে ক্লিক করুন।</p>
        </div>
    </div>

    <div id="screen-setup" class="app-screen">
        <div class="bkash-pink p-4 text-white flex items-center gap-4">
            <i class="fa-solid fa-arrow-left cursor-pointer" onclick="showScreen('screen-home')"></i>
            <span class="font-medium">সালামি পাঠান</span>
        </div>
        <div class="p-6">
            <div class="border rounded-lg p-4 bg-gray-50">
                <p class="text-xs text-gray-400 uppercase font-bold mb-1">Receiver</p>
                <p class="font-bold text-gray-800 text-lg">NAFIJ</p>
                <p class="text-gray-500">01882593289</p>
            </div>
            <div class="mt-6 border-b pb-2">
                <p class="text-xs text-gray-400 font-bold mb-1">AMOUNT</p>
                <span class="text-3xl font-bold text-bkash">৳</span>
                <input type="number" placeholder="0" class="text-3xl font-bold outline-none w-40 ml-2">
            </div>
            <button onclick="showScreen('screen-pin')" class="w-full bkash-pink text-white py-4 rounded-xl mt-10 font-bold shadow-lg">পরবর্তী ধাপ</button>
        </div>
    </div>

    <div id="screen-pin" class="app-screen">
        <div class="flex flex-col items-center pt-16 px-6">
            <div class="w-16 h-16 bg-pink-50 rounded-full flex items-center justify-center mb-4">
                <i class="fa-solid fa-lock text-yellow-500 text-2xl"></i>
            </div>
            <p class="font-bold text-gray-800 text-lg">বিকাশ পিন দিন</p>
            <p class="text-xs text-gray-400 mt-1">Nafij-কে সালামি পাঠাতে পিন দিন</p>
            <div class="flex gap-4 my-8" id="pin-container">
                <div class="pin-dot"></div><div class="pin-dot"></div><div class="pin-dot"></div><div class="pin-dot"></div><div class="pin-dot"></div>
            </div>
            <div class="grid grid-cols-3 gap-3 w-full">
                <button class="numpad-btn" onclick="tapPin()">1</button>
                <button class="numpad-btn" onclick="tapPin()">2</button>
                <button class="numpad-btn" onclick="tapPin()">3</button>
                <button class="numpad-btn" onclick="tapPin()">4</button>
                <button class="numpad-btn" onclick="tapPin()">5</button>
                <button class="numpad-btn" onclick="tapPin()">6</button>
                <button class="numpad-btn" onclick="tapPin()">7</button>
                <button class="numpad-btn" onclick="tapPin()">8</button>
                <button class="numpad-btn" onclick="tapPin()">9</button>
                <button class="numpad-btn bg-gray-100" onclick="resetPin()">C</button>
                <button class="numpad-btn" onclick="tapPin()">0</button>
                <button class="numpad-btn text-bkash" onclick="showScreen('screen-home')"><i class="fa-solid fa-circle-arrow-right"></i></button>
            </div>
        </div>
    </div>

    <div id="screen-success" class="app-screen bg-gray-50">
        <div class="bkash-pink p-12 text-center text-white">
            <div class="w-20 h-20 bg-white rounded-full flex items-center justify-center mx-auto mb-4">
                <i class="fa-solid fa-check text-bkash text-4xl"></i>
            </div>
            <p class="text-xl font-bold">আপনার সালামি সফল হয়েছে</p>
        </div>
        <div class="p-6 -mt-6">
            <div class="bg-white rounded-xl shadow-md p-6 space-y-4">
                <div class="flex justify-between border-b pb-2">
                    <span class="text-gray-400 text-sm">প্রাপক</span>
                    <span class="font-bold">NAFIJ</span>
                </div>
                <div class="flex justify-between border-b pb-2">
                    <span class="text-gray-400 text-sm">নম্বর</span>
                    <span class="font-bold text-bkash">01882593289</span>
                </div>
                <div class="flex justify-between border-b pb-2">
                    <span class="text-gray-400 text-sm">সময়</span>
                    <span class="font-medium" id="current-time"></span>
                </div>
                <div class="pt-4 text-center">
                    <p class="text-xs text-gray-400 uppercase font-bold">Transaction ID</p>
                    <p class="font-bold text-gray-700">9K20M88F4L</p>
                </div>
            </div>
            <button onclick="showScreen('screen-home')" class="w-full border-2 border-bkash text-bkash py-3 rounded-xl mt-6 font-bold">ফিরে যান</button>
        </div>
    </div>

    <script>
        function showScreen(id) {
            document.querySelectorAll('.app-screen').forEach(s => s.classList.remove('active'));
            document.getElementById(id).classList.add('active');
            if(id === 'screen-success') {
                document.getElementById('current-time').innerText = new Date().toLocaleString();
            }
        }

        let pinCount = 0;
        function tapPin() {
            const dots = document.querySelectorAll('.pin-dot');
            if(pinCount < 5) {
                dots[pinCount].classList.add('filled');
                pinCount++;
            }
            if(pinCount === 5) {
                setTimeout(() => {
                    showScreen('screen-success');
                    resetPin();
                }, 400);
            }
        }

        function resetPin() {
            pinCount = 0;
            document.querySelectorAll('.pin-dot').forEach(d => d.classList.remove('filled'));
        }
    </script>
</body>
</html>
