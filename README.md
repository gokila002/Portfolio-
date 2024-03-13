# Portfolio-
Portfolio 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PSS Transport</title>
    <link rel="stylesheet" href="./style.css" />
    <style>
         body {
            font-family: Arial, sans-serif;
            color: rgb(5, 5, 5);
            margin: 0;
            padding: 0;
          
        }

       

        form {
           
            margin-top: 50px;
            margin-bottom: 100px;
            max-height: 100%;
            max-width: 400px;
            margin: 20px auto;
            background: #f5f4f4d4;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }

        .seat-container {
            display: grid;
            grid-template-columns: repeat(6, 1fr);
            gap: 4px;
        }

        .seat {
            width: 30px;
            height: 30px;
            font-family: Arial, sans-serif;
            color: rgb(255, 255, 255);
            background-color: #7c7b7b;
            border: 1px solid #ccc;
            text-align: center;
            line-height: 30px;
            cursor: pointer;
        }

        .seat.selected {
         
            background-color: #4caf50;
            color: #fff;
        }






        .bus-details {
            width: 20%;
            margin: 20px auto;
            background: #f5f5f5d4;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }

        .bus-details h2 {
            color: white;
        }

        .bus-info {
            display: flex;
            justify-content: space-between;
            margin-bottom: 15px;
        }

        .bus-info span {
            font-weight: bold;
        }







        

        .form-label {
            font-weight: bold;
            display: block;
            margin-bottom: 5px;
        }

        .button-group {
            text-align: center;
            margin-top: 15px;
        }

        button {
            background-color: #4764e4;
            color: #fff;
            padding: 10px 20px;
            font-size: 16px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }

        button:hover {
            background-color: #45a049;
        }

        .payment-summary {
            margin-top: 15px;
            font-size: 18px;
        }




        
    </style>
</head>
<body>

    <!-- Background & animion & navbar & title -->
  <div class="container-fluid">
    <!-- Background animtion-->
        <div class="background">
          

    <form action="confirmation.php" method="post">
        
        <div class="bus-details1">
            <h2>ARS Transport</h2><br>
    
            <div class="bus-info">
                <span>Bus Number:</span>
                <span>TN42C3123</span>
            </div>
    
            <div class="bus-info">
                <span>Departure Time:</span>
                <span>10:00 PM</span>
            </div>
    
            <div class="bus-info">
                <span>Departure Point:</span>
                <span>Covai</span>
            </div>
    
            <div class="bus-info">
                <span>Destination:</span>
                <span>Pollachi</span>
            </div>
    
            <div class="bus-info">
                <span>Available Seats:</span>
                <span>32</span>
            </div><br>

       

        <div class="form-group">
            <label class="form-label">Select Seat(s)</label>
            <div class="seat-container" id="seatContainer"></div>
        </div>

        <div class="payment-summary" id="paymentSummary">Total Amount: $0</div>

        <div class="button-group">
            <a href="./paymentdetails.html"> <button type="button" class="book-button">Proceed To confirmation</button></a>
        </div>
    </div>
    </form>

    <script>
        document.addEventListener('DOMContentLoaded', function () {
            const seatContainer = document.getElementById('seatContainer');
            const paymentSummary = document.getElementById('paymentSummary');

            // Simulated seat data, replace with dynamic data from your server
            const totalSeats = 32;
            const seatPrice = 950; // Price per seat

            let selectedSeats = [];

            for (let i = 1; i <= totalSeats; i++) {
                const seatElement = document.createElement('div');
                seatElement.className = 'seat';
                seatElement.textContent = i;

                seatElement.addEventListener('click', function () {
                    seatElement.classList.toggle('selected');

                    if (seatElement.classList.contains('selected')) {
                        selectedSeats.push(i);
                    } else {
                        selectedSeats = selectedSeats.filter(seat => seat !== i);
                    }

                    updatePaymentSummary();
                });

                seatContainer.appendChild(seatElement);
            }

            function updatePaymentSummary() {
                const totalPrice = selectedSeats.length * seatPrice;
                paymentSummary.textContent = `Total Amount: $${totalPrice}`;
            }
        });
    </script>


<center>
  <a href="./busdetails.html"> <button type="button" class="book-button">BACK</button></a>
</center> 

</body>
</html>
