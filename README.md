<!DOCTYPE html>
<html lang="en">

<head>
    <!-- Coded by Sumanjay @cyberboysumanjay on 5th August 2020 -->

    <!--Let browser know website is optimized for mobile-->
    <meta name="viewport" content="=device-width, initial-scale=1.0" />

    <!-- Meta Tags -->
    <meta name="author" content="Sumanjay">
    <meta name="description" content="Create Payment Link of your UPI ID!">

    <link rel="icon" href="https://telegra.ph/file/2f094c81af60c83f28f84.png" type="image/png" />
    <link rel="stylesheet" type="text/css" href="/static/css/style.css" />
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.0.0/animate.min.css" />
    <title>UPI Link</title>


    <!-- Global site tag (gtag.js) - Google Analytics -->
    <script async src="https://www.googletagmanager.com/gtag/js?id=UA-174919510-1"></script>
    <script>
        window.dataLayer = window.dataLayer || [];

        function gtag() {
            dataLayer.push(arguments);
        }
        gtag('js', new Date());

        gtag('config', 'UA-174919510-1');
    </script>

</head>

<body>

    <div class="card">
        <div class="banner2">
            <img height=180px; src="https://telegra.ph/file/2f094c81af60c83f28f84.png">
        </div>
        <h2 class="create-name">Create shareable UPI Payment links!</h2>

        <p class="create">Just add your UPI ID here<br><b>https://upayi.me/<your-upi-id>/<amount></b><br><br>Or,<br><b>Use our UPI Link Generator Tool</b></p>
        <div class="actions">
            <div class="pay-btn">
                <input type="text" placeholder="Enter your UPI ID" id="upiid">
                <input type='number' step='1.0' placeholder="Enter Amount (Optional)" id="amountid">
                <input type="text" placeholder="Get your UPI Link" id="upilink" hidden disabled>
                <button onclick=getLink()>
                    <span class="tooltiptext" id="myTooltip">Create and Copy Link</span>
                </button>
                <br><br>
                <a href="https://upayi.me/sumanjay@ybl">
                    <button>    
                        <span>Donate</span>
                    </button>
                </a>
                <br>
            </div>
        </div>

        <div class="desc link"> <a href="https://github.com/cyberboysumanjay">Made with <span class="love">❤️</span> by Sumanjay</a></div>

    </div>

    <script>
        var upiid = document.getElementById("upiid");
        var amountid = document.getElementById("amountid");
        var upilink = document.getElementById("upilink");
        var tooltip = document.getElementById("myTooltip");

        function getLink() {
            if (upiid.value.indexOf("@") != -1) {
                var amount = "";
                console.log(amountid.value);
                console.log(amountid.value.length);
                console.log(typeof(amountid.value))
                if (isNumeric(amountid.value)) {
                    amount = "/" + amountid.value;
                }
                upilink.value = "https://upayi.me/" + upiid.value + amount;
                upilink.style.display = "block";
                navigator.clipboard.writeText(upilink.value);
                var copyText = document.getElementById("upilink");
                tooltip.innerHTML = "Copied to Clipboard!";
            } else {
                tooltip.innerHTML = "Invalid UPI ID Entered";
            }
        }

        function isNumeric(n) {
            return !isNaN(parseFloat(n)) && isFinite(n);
        }
    </script>
</body>

</html>
