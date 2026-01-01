This project demonstrates the implementation of the Sobel edge detection operator using both serial and parallel processing techniques. The project compares the performance of the two implementations on an animal image dataset, analyzing the time efficiency and speedup achieved through parallel processing.

# Project Overview
The Sobel edge detection algorithm is widely used in image processing to detect edges by calculating intensity gradients. This project includes:

A serial implementation where each image is processed sequentially.
A parallel implementation using the PyMP library to process multiple images simultaneously across multiple CPU cores.
A performance comparison of the two approaches.
Dataset
The project uses the Animal Image Classification Dataset from Kaggle, which includes 3,000 images of animals (cats, dogs, and snakes). For simplicity, all images are combined into a single folder named "Animals".

Dataset Source: Animal Image Classification Dataset on Kaggle
Categories: Cats, Dogs, Snakes
Image Specifications: Each image is a 256x256 RGB JPG file
Project Structure
input_folder: Folder containing the raw images.
serial_output_folder: Folder where edge-detected images processed serially are saved.
parallel_output_folder: Folder where edge-detected images processed in parallel are saved.
Implementation Details
Serial Implementation
The Serial Processing Module reads each image one by one, applies the Sobel operator to detect edges, and saves the output. This approach processes images sequentially, which can be time-consuming for large datasets.

Parallel Implementation
The Parallel Processing Module uses the PyMP library to split image processing tasks across multiple threads, enabling multiple images to be processed at once. This leverages multi-core processing capabilities to reduce overall execution time.

Performance Measurement and Comparison
The project measures and compares the execution times for both serial and parallel processing modes. It calculates the speedup factor to quantify the efficiency gains from parallel processing.

# Requirements
Install the required libraries using pip:  

    pip install numpy opencv-python pymp-pypi ipywidgets

# Code Description
Key Functions
process_images_serial:

Applies Sobel edge detection to images in the input folder sequentially.
Saves each edge-detected image to serial_output_folder.
Records and prints the total time taken for serial processing.
process_images_parallel:

Uses PyMP to process images in parallel across multiple threads.
Each thread applies Sobel edge detection and saves images to parallel_output_folder.
Records and prints the total time taken for parallel processing.
on_process_button_clicked:

Button click handler that initiates processing based on the selected compute mode (Serial or Parallel).
Runs both modes and compares execution times, printing the time difference.
Widgets and UI
Dropdown: Allows users to select the processing mode (Serial or Parallel).
Button: Starts the processing and displays timing results.
Results
Performance Metrics: The notebook outputs the execution time for both serial and parallel implementations.
Speedup Factor: The project calculates and displays the speedup factor achieved through parallel processing, helping to demonstrate the effectiveness of parallelization.
Example Results
Example output of processing times:
         Serial processing time: 7.5011 seconds
         Parallel processing time: 3.1513 seconds
         Parallel processing was faster by 4.3498 seconds

Conclusion
This project demonstrates how parallel processing can significantly reduce the time required for computationally intensive tasks like edge detection on large datasets. By comparing serial and parallel implementations, we see the practical benefits of utilizing multi-core processing for high-performance image processing tasks.

License
This project is licensed under the MIT License.




