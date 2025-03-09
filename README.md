<body>
  <h1>SMS Spam Detection</h1>
  <p>This project implements a deep learning model to classify SMS messages as either "ham" (not spam) or "spam" using TensorFlow and Keras.</p>

  <h2>Table of Contents</h2>
  <ul>
      <li><a href="#introduction">Introduction</a></li>
      <li><a href="#dataset">Dataset</a></li>
      <li><a href="#model-architecture">Model Architecture</a></li>
      <li><a href="#training">Training</a></li>
      <li><a href="#results">Results</a></li>
      <li><a href="#conclusion">Conclusion</a></li>
      <li><a href="#installation">Installation</a></li>
      <li><a href="#usage">Usage</a></li>
      <li><a href="#license">License</a></li>
  </ul>

  <h2 id="introduction">Introduction</h2>
  <p>The SMS Spam Detection project aims to classify SMS messages into two categories: "ham" and "spam". The model is trained on a dataset of labeled SMS messages and can predict the class of new messages.</p>

  <h2 id="dataset">Dataset</h2>
  <p>The dataset used in this project consists of:</p>
  <ul>
      <li>Training messages: 4,179</li>
      <li>Validation messages: 1,392</li>
  </ul>
  <p>The dataset is provided in TSV format, with each message labeled as either "ham" or "spam".</p>

  <h2 id="model-architecture">Model Architecture</h2>
  <p>The model architecture consists of:</p>
  <ul>
      <li>Embedding layer to convert words into dense vectors</li>
      <li>LSTM layer for sequence processing</li>
      <li>Dense layers for classification</li>
      <li>Dropout layer to prevent overfitting</li>
  </ul>

  <h2 id="training">Training</h2>
  <p>The model is trained using:</p>
  <ul>
      <li>Optimizer: RMSprop</li>
      <li>Loss function: Binary Crossentropy</li>
      <li>Metrics: Accuracy</li>
      <li>Epochs: 10</li>
  </ul>
  <p>The model uses early stopping to prevent overfitting during training.</p>

  <h2 id="results">Results</h2>
  <p>The model achieved a validation accuracy of approximately 98.33% after training. The loss decreased significantly over the epochs, indicating effective learning.</p>

  <h2 id="conclusion">Conclusion</h2>
  <p>The SMS Spam Detection project demonstrates the effectiveness of LSTM networks in text classification tasks. The model can accurately classify SMS messages as spam or ham, making it useful for filtering unwanted messages.</p>

  <h2 id="installation">Installation</h2>
  <p>To run this project, ensure you have the following installed:</p>
  <pre><code>pip install tensorflow pandas nltk</code></pre>

  <h2 id="usage">Usage</h2>
  <p>To use the model, you can input a message and the model will predict whether it is spam or ham.</p>

  <h3>Example Code</h3>
  <pre><code>
def predict_message(pred_text):
  p = model.predict(preprocessing(pd.Series([pred_text])))[0]
  return (p[0], ("ham" if p < 0.5 else "spam"))

pred_text = "Congratulations! You've won a free ticket."
prediction = predict_message(pred_text)
print(prediction)
  </code></pre>

  <h2 id="license">License</h2>
  <p>This project is licensed under the MIT License. See the <a href="LICENSE">LICENSE</a> file for details.</p>
</body>
