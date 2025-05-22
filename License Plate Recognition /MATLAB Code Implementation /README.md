
### **Step-by-Step Explanation of Your MATLAB LPR Code**

1. **Initialize Environment**
   Clear workspace and close all figures


2. **Read and Display Input Image**
   Load the vehicle image and show the original

3. **Convert RGB Image to Grayscale**
   Simplify image for processing

4. **Manual Image Dilation (Noise Reduction)**
   Dilate horizontally by comparing each pixel with neighbors to enhance edges and remove noise

   Then display the dilated image.

5. **Horizontal Edge Processing**

   * Calculate differences of pixel intensities between vertically adjacent pixels to detect horizontal edges.
   * Sum differences greater than threshold (20) column-wise to build a horizontal histogram.
   * Find peak column index (max\_horz) with maximum edge activity.
   * Plot horizontal edge histogram.

6. **Smooth Horizontal Histogram (Low Pass Filter)**
   Average over a sliding window (41 columns) to smooth histogram and reduce noise.

7. **Apply Dynamic Threshold on Horizontal Histogram**

   * Remove histogram values below average by setting them and corresponding image columns to zero.
   * Plot filtered horizontal histogram.

8. **Vertical Edge Processing**

   * Similar to horizontal step but process edges row-wise by calculating differences between horizontally adjacent pixels.
   * Build vertical histogram, find max row (max\_vert), and plot.

9. **Smooth Vertical Histogram**
   Apply low pass filter with sliding window (41 rows) to vertical histogram.

10. **Apply Dynamic Threshold on Vertical Histogram**
    Zero out histogram values below average and corresponding image rows.

11. **Display Filtered Image After Edge Processing**

12. **Find Probable License Plate Regions**

    * Detect edges in histograms where non-zero values start and end — collect start and end indices in `column` and `row` arrays.

13. **Ensure Even Number of Coordinates**
    Append image width/height if odd number of detected regions to maintain pairs.

14. **Extract Region of Interest (ROI)**

    * For each candidate rectangular region (from paired row and column indices), check if it contains the maximum edge peaks (`max_horz` and `max_vert`).
    * Zero out regions not containing the peaks — this filters out unlikely plate areas.

15. **Display Final Processed Image**
    The image shows only the probable license plate area highlighted.

