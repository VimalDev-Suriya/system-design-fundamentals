# Paytm's QR Code payment processing:


## Problems to be solved in order to implment the QR code scan:
1. Without using expensive hardwares, like card swipe machine, we need to have the payment system for low revenue merchants
2. SHould work efficeintly even in lower network signals like 2G
3. Merchant should know about the payments was actually done

SO the problem was solved just by using the simple static QR code and a loud-speaker to confirm the payment.

## How it works

1. Paytm shares the simple static QR code to the merchants. These QR code holds the VPA (Virtual Payment Address) for the individual merchants
2. When customer scans the QR code (irrespective the servive provider (GPay / PhonePay etc)), customers enter the amount and PIN for auth
3. NPCI will process the payment via UPI rails, based on the event - if the UPI payment was successful, then PaytM will detect the event
4. Push those event to the loud speaker box (a IOT device) which will be backed by 2G and works in 4G with SIM
5. Then Sound box will speaks the incoming event - this also have the queue.

## Need to Know:

1. How UPI - Unified Payments Interface (yet to understand) (Bank to Bank)
2. How bank transaction works
