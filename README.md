Bridging the Gap: Scattering Transforms vs. CNNs
This repository contains a PyTorch experiment comparing the Wavelet Scattering Transform (WST) to a Convolutional Neural Network (CNN) on the MNIST dataset, using the Kymatio library.

The experiment tests if WST filters can be treated as trainable parameters, similar to a CNN's convolutional filters.

Models Compared
All models use a scattering front-end and a single linear classifier. The only difference is what part is trained.

1. Baseline (Fixed WST):

Filters: Fixed (standard Kymatio wavelets)

Classifier: Trainable

2. Trainable Wavelets (WST-Initialized):

Filters: Trainable (initialized as wavelets)

Classifier: Frozen

3. Trainable Random (CNN-Style):

Filters: Trainable (initialized randomly)

Classifier: Frozen

📊 Results & Key Findings
This experiment's results highlight the power of wavelet filter initialization.

Model Configuration	Filter Initialization	Accuracy
Fixed WST	Fixed Wavelets	98.01%
Trainable WST	Wavelet-Initialized	98.71%
CNN-Style	Random-Initialized	93.97%

ייצוא אל Sheets

Conclusion
The key takeaway is that structure matters.

Wavelets > Random: Both models using wavelet-based filters (fixed or trainable) dramatically outperformed the randomly initialized model. This shows the wavelet structure itself is a highly effective feature extractor.

Training Helps (a little): The best performance came from fine-tuning the wavelet filters (98.71%). This suggests the WST provides an excellent starting point, which can be slightly optimized for the specific task.

In short, the Wavelet Scattering Transform acts as a powerful, pre-trained "first layer," far superior to a "blank slate" random initialization.

⚙️ How to Run
Clone the repository:

Bash

git clone <your-repo-url>
cd <your-repo-name>
Open and run the notebook: Run Bridging the Gap Between the Scattering Transform and Convolutional Neural Network.ipynb in Google Colab, VS Code, or a local Jupyter environment.

Dependencies: The notebook installs its own requirements. If you need to install them manually:

Bash

pip install torch torchvision kymatio numpy
