require('@tensorflow/tfjs-backend-cpu');
require('@tensorflow/tfjs-backend-webgl');
const cocoSsd = require('@tensorflow-models/coco-ssd');

(async () => {
  const img = document.getElementById('img');

  // Load the model.
  const model = await cocoSsd.load();

  // Classify the image.
  const predictions = await model.detect(img);

  console.log('Predictions: ');
  console.log(predictions);
})();
