function generateQRCode() {
  let upiId = document.getElementById("upi-id").value;
  let amount = document.getElementById("amount").value;

  if (!upiId || !amount) {
    alert("Please enter a valid UPI ID and amount.");
    return;
  }

  let upiURL = `upi://pay?pa=${upiId}&pn=Recipient&am=${amount}&cu=INR&tn=Payment`;

  // Clear previous QR code
  document.getElementById("qrcode").innerHTML = "";

  // Generate new QR code
  new QRCode(document.getElementById("qrcode"), {
    text: upiURL,
    width: 200,
    height: 200
  });
}
