
<!doctype html>

<html lang="en">

<head>

    <style>

        :root {

            --gradient: linear-gradient(to left top, #DD2476 10%, #FF512F 90%) !important;

        }

        body {

            background: #111 !important;

        }

        .card {

            background: #222;

            border: 1px solid #dd2476;

            color: rgba(250, 250, 250, 0.8);

            margin-bottom: 2rem;

        }

        .btn {

            border: 5px solid;

            border-image-slice: 1;

            background: var(--gradient) !important;

            -webkit-background-clip: text !important;

            -webkit-text-fill-color: transparent !important;

            border-image-source: var(--gradient) !important;

            text-decoration: none;

            transition: all .4s ease;

        }

        .btn:hover,

        .btn:focus {

            background: var(--gradient) !important;

            -webkit-background-clip: none !important;

            -webkit-text-fill-color: #fff !important;

            border: 5px solid #fff !important;

            box-shadow: #222 1px 0 10px;

            text-decoration: underline;

        }

        .title {

            text-align: center;

            color: white;

            text-transform: capitalize;

        }

        .underline {

            height: 3px;

            align-items: center;

            width: 100%;

            background-color: white;

        }

        .full {

            margin-top: 40px;

        }

        .btns {

            display: flex;

            justify-content: space-around;

        }

        .text-muted {

            margin-left: 10px;

            margin-top: 41px;

            color: #6c757d !important;

            white-space: break-spaces;

        }

        .card-body {

            height: 200px;

            overflow: scroll;

        }

        .card{

            top: 150px;

        }

    </style>

    <title>random jokes</title>

    <!-- Required meta tags -->

    <meta charset="utf-8">

    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

    <!-- Bootstrap CSS -->

    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css"

        integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">

</head>

<body>

    <div class="title">

        <h2>new jokes</h2>

        <div class="underline"></div>

    </div>

    <div class="col-md-5 mt-5  full">

        <div class="card ">

            <div class="card-body " style="max-width: 400px; ">

                <p class=" text-muted" id="jokes">

                </p>

            </div>

            <div class="btns">

         <a href="#" class="btn " id="pre">pre</a>  

                <a href="#" class="btn " id="next">NEXT</a>

                

            </div>

        </div>

    </div>

    <!-- Optional JavaScript -->

    <!-- jQuery first, then Popper.js, then Bootstrap JS -->

    <script src="https://code.jquery.com/jquery-3.3.1.slim.min.js"

        integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo"

        crossorigin="anonymous"></script>

    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js"

        integrity="sha384-UO2eT0CpHqdSJQ6hJty5KVphtPhzWj9WO1clHTMGa3JDZwrnQq4sF86dIHNDz0W1"

        crossorigin="anonymous"></script>

    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js"

        integrity="sha384-JjSmVgyd0p3pXB1rRibZUAYoIIy6OrQ6VrjIEaFf/nJGzIxFDsf4x0xIM+B07jRM"

        crossorigin="anonymous"></script>

</body>

<script>

    const jokes = [

        {

            id: 1,

            text: ' “Fix the cause, not the symptom.”    – Steve Maguire '

        },

        {

            id: 2,

            text: '“Perfection is achieved not when there is nothing more to add, but rather when there is nothing more to take away.” – Antoine de Saint-Exupery'

        },

        {

            id: 3,

            text: 'Girl: Do you drink?Programmer: No. Girl: Have Girlfriend? Programmer: No. Girl: Then how do you enjoy life? Programmer: I am Programmer'

        },

        {

            id: 4,

            text: 'Me: Will you be my Valentine? Girl: No way Me: sudo will you be my Valentine? Girl: Yes..yes..yes! Let’s go!'

        },

        {

            id: 5,

            text: '“Any fool can write code that a computer can understand. Good programmers write code that humans can understand.” – Martin Fowler'

        },

        {

            id: 6,

            text: '“First, solve the problem. Then, write the code.” – John Johnson'

        },

        {

            id: 7,

            text: '“Experience is the name everyone gives to their mistakes.” – Oscar Wilde'

        },

        {

            id: 8,

            text: '“Knowledge is power.” – Francis Bacon'

        },

        {

            id: 9,

            text: '“ Code is like humor. When you have to explain it, it’s bad.” – Cory House'

        },

        {

            id: 10,

            text: '“Make it work, make it right, make it fast.” – Kent Beck'

        },

        {

            id: 11,

            text: ' पप्पू भागता हुआ आया और बोला...  पापा जल्दी से तैयार हो जाओ . पापा-क्यों ? . पप्पू-अरे आज लड़की वाले मुझे देखने आ रहे हैं . पापा-अबे तुझे किसने कहा? पप्पू-अरे वो पड़ोस में शर्मा अंकल हैं न . मैंने उनकी लड़की को छेड़ दिया, तो वो बोले देख लेंगे तुझे। . शर्मा अंकल के आने से पहले पापा ने पप्पू को देख लिया . दे थप्पड़, दे थप्पड़, दे थप्पड़ '

        },

    ];

    const joke = document.getElementById('jokes');

    const nbtn = document.getElementById('next');

    const prebtn = document.getElementById('pre');

    let currentitem = 0;

    window.addEventListener("DOMContentLoaded", function () {

        // console.log('hi')

        const item = jokes[currentitem];

        joke.textContent = item.text;

    })

    let count = 0;

    nbtn.addEventListener("click", function () {

        count++;

        if (count < 12) {

            currentitem++;

            const item = jokes[currentitem];

            joke.textContent = item.text;

        }

        else {

            alert('i think you see all content')

        }

    })

    prebtn.addEventListener("click", function () {

        count--;

        if (count => 0) {

            currentitem--;

            const item = jokes[currentitem];

            joke.textContent = item.text;

        }

        else {

            alert('i think you see all content')

        }

    })

</script>

</html>
