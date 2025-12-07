DWT–PSO Image Watermarking

A simple and smart way to hide watermarks inside images using Wavelets + Optimization.

This project implements a digital watermarking system that uses DWT (Discrete Wavelet Transform) and PSO (Particle Swarm Optimization) to embed a watermark into an image in a way that’s almost invisible but still very hard to remove.

The idea is simple:

Put the watermark in a smart place and with the perfect strength so the image still looks the same — but the watermark survives attacks.

The full explanation is available in the project report.

🚀 What This Project Does

Takes a cover image (the main image)

Takes a watermark (logo, text, or binary image)

Breaks the cover image into wavelet levels using DWT

Embeds the watermark inside specific frequency bands

Uses PSO to find the best embedding strength

Reconstructs the watermarked image

Extracts the watermark back — even after noise, compression, etc.

It's built to keep a balance between:

Imperceptibility → Your image still looks normal

Robustness → Watermark survives edits/attacks

Accuracy → Extracted watermark stays recognizable

🧩 How The Method Works (Simple Explanation)

Convert both images to grayscale and resize them

Apply 3-level DWT to the cover image

Choose a wavelet band (HL/Approximation) to hide the watermark

Insert the watermark by:

modified_band = original_band + alpha * watermark


Rebuild the image → now it contains the hidden watermark

Use PSO to search for the best α (watermark strength):

Too small → watermark becomes weak

Too large → image gets distorted

The optimized α gives the best visual + watermark extraction quality

Finally, extract the watermark from the watermarked image

The report (pages 23–24) shows a clear flow diagram of all 12 steps. 

Digital Watermark using DWT-PS…

📊 How Well It Performs

Using PSO vastly improves the results:

Metric	Before Optimization	After Optimization
PSNR	~34 dB	40+ dB
SSIM	0.95	≈1.0
NCC	0.82	0.99
BER	0.12	0.01

This means:

The watermarked image looks almost identical

Extracted watermark matches the original very closely

Errors drop sharply

These numbers are from the experiments documented in the report (pages 40–41). 

Digital Watermark using DWT-PS…

🛠️ Requirements

Install dependencies:

pip install opencv-python pywavelets pyswarms numpy matplotlib scikit-image

▶️ How to Run the Code

Put your cover and watermark images in the project folder

Update the paths at the top of the Python file

Run:

python "Digital watermark using DWT-PSO.py"


You’ll get:

watermarked.png → Your final watermarked image

extracted.png → Watermark extracted back from the image

📂 Project Files
📁 Digital Watermarking Project
│
├── Digital watermark using DWT-PSO.py        # Main code
├── Digital Watermark using DWT-PSO Report.pdf  # Full internship report
│
├── /input
│   ├── cover.png
│   ├── watermark.png
│
└── /output
    ├── watermarked.png
    ├── extracted.png

Credits:-

This project was created as part of a summer internship on watermarking research.
All concepts, results, and evaluation details are documented in the internship report 


 License

Feel free to use this code for research & learning.
If you use it, giving credit.
