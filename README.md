# Fabric defect detection and defect localization
The approach used here is based on image segmentation, which involves partitioning the image into different regions based on their visual characteristics.

The project follows the following steps:

- Image Loading: The fabric image is loaded from the provided path. This image serves as the input for the defect detection algorithm.
- Grayscale Conversion: The color fabric image is converted to grayscale. This simplifies the subsequent image processing steps by reducing the dimensionality to a single channel.
- Image Segmentation: Image segmentation is performed on the grayscale image using a thresholding technique. In this case, the Otsu's thresholding method is used to obtain a binary image. This technique automatically calculates an optimal threshold value to separate the fabric defects from the background.
- Connected Component Labeling: The connected components in the binary image are labeled using the skimage.measure.label function. Each connected component is assigned a unique label.
- Defect Detection: The labeled connected components are analyzed to determine if they represent fabric defects. A contour-based approach is used to calculate the contour area of each labeled region. If the contour area exceeds a predefined threshold (in this case, 100 pixels), it is considered as a potential defect.
- Defect Localization: For the identified defects, a defect mask is created by combining the binary masks of the labeled regions that represent defects. This defect mask highlights the exact location and extent of the defects in the fabric image.
- Visualization: The results are visualized using matplotlib. The original fabric image, defect mask, and the fabric image with the defects localized and masked are displayed in a figure.

# Project Benefits and Use Cases:

This fabric defect detection and localization project offers several benefits and can be applied in various use cases:

- Quality Control in Textile Industry: The project enables automated fabric defect detection, eliminating the need for manual inspection and reducing human error. It can be integrated into the production line for real-time quality control.
- Efficient Fabric Inspection: By localizing and highlighting defects, the system allows fabric manufacturers to quickly identify and address quality issues, leading to improved production efficiency.
- Reduced Fabric Waste: Early detection of defects enables proactive measures to salvage or repair defective areas, minimizing fabric waste and optimizing resource utilization.
- Improved Product Quality: By detecting and localizing defects accurately, the system ensures that only high-quality fabric is used in the manufacturing process, leading to superior end products.
