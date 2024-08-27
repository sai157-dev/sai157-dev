!pip install qrcode

import qrcode

# Data to be encoded
data = "https://example.com"

# Creating an instance of QRCode
qr = qrcode.QRCode(
    version=1,  # controls the size of the QR Code, can be an integer from 1 to 40
    error_correction=qrcode.constants.ERROR_CORRECT_L,  # controls the error correction used for the QR Code
    box_size=10,
    border=4,
)

# Adding data to the instance
qr.add_data(data)
qr.make(fit=True)

# Creating an image from the QR Code instance
img = qr.make_image(fill_color="black", back_color="white")

# Saving the image
img.save("qrcode.png")
