# WAD2-Project

<!DOCTYPE html>
<html>

<h1>Travel Planner</h1>

<head>
    <!-- Bootstrap CSS -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.0/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-gH2yIJqKdNHPEq0n4Mqa/HGKIhSkIHeL5AyhkYV8i59U5AR6csBvApHHNl/vI1Bx" crossorigin="anonymous">
    <script src="https://polyfill.io/v3/polyfill.min.js?features=default"></script>
    <script src="https://unpkg.com/axios/dist/axios.min.js"></script>

    <h1>Trial ISS API</h1>
</head>

<body>
    <div id="displayres"></div>

    <script>
        var url = "https://airlabs.co/api/v9/flight?flight_iata=SIN&api_key=875e85a0-4a57-48b9-9ad9-7b29565294a3&flight_icao=WSSS";

        axios.get(url)
        .then(response => {
            console.log(response.data)

            var flightdata = response.data;
            var flightkeys = Object.keys(flightdata)
            console.log(flightkeys)
            
            var displaydiv = document.getElementById("displayres")
            var str = ""
            for (flightkey of flightkeys) {
                console.log(flightdata[flightkey])
                str += flightdata[flightkey]
            }

            displaydiv.innerText = str
        })
        .catch(error => {
            console.log(error.message)
        })
    </script>

    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.0/dist/js/bootstrap.bundle.min.js" integrity="sha384-A3rJD856KowSb7dwlZdYEkO39Gagi7vIsF0jrRAoQmDKKtQBHUuLZ9AsSv4jD4Xa" crossorigin="anonymous"></script>

    <script>
    
        var myHeaders = new Headers();
        myHeaders.append("apikey", "xxx");

        var requestOptions = {
        method: 'GET',
        redirect: 'follow',
        headers: myHeaders
        };
        
        fetch("https://api.apilayer.com/currency_data/convert?to=SGD&from=USD&amount=10", requestOptions)
        .then(response => response.text())
        .then(result => console.log(result))
        .catch(error => console.log('error', error));

    </script>
    
</body>

</html>

