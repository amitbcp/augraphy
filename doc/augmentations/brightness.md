# Brightness

The Brightness augmentation adjusts the brightness of the whole image by a chosen multiplier.


| Parameter                | Description                                                                       |
|--------------------------|-----------------------------------------------------------------------------------|
| `range`                  | The range of values to be chosen at random for the brightness multiplier applied. |
| `min_brightness`         | Flag to enable min brightness intensity value in the augmented image.             |
| `min_brightness_value`   | Pair of ints determining the minimum brightness intensity of augmented image.     |
| `p`                      | The probability that this augmentation will be applied.                           |


**Example Usage:**
```python
    from matplotlib import pyplot as plt
    from time import time
    import cv2
    import numpy as np

    start_time = time()

    # create a blank image
    image = np.full((1500, 1500,3), 128, dtype="uint8")

    # insert text into image
    for y in range(200, 1300, 100):
        cv2.putText(
            image,
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit",
            (250, y),
            cv2.FONT_HERSHEY_SIMPLEX,
            1,
            0,
            3,
        )


    brightness= Brightness(range=(1.5, 2))

    img_brightness = brightness(image)

    elapsed_time = time() - start_time
    # processing time
    print("Elapsed time = " + str(elapsed_time) + " seconds")


    # display output

    plt.figure()
    plt.subplot(121)
    plt.imshow(image)
    plt.title("Input image")
    plt.subplot(122)
    plt.imshow(img_brightness)
    plt.title("Brightness augmentation")

```

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1zPuAFgW8BdgX9tH9grorp_V3B7FswVUq?usp=sharing)
