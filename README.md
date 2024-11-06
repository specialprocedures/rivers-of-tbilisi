# Rivers of Tbilisi Analysis

This project is a quick piece of analysis for my friend Tim, who runs the [@riversoftbilisi](https://www.instagram.com/riversoftbilisi/) Instagram account. 

Tim has been documenting the paths of Tbilisi's smaller rivers and streams, following submerged waterways and highlighting challenges with urban sprawl and pollution. I told him I'd "do something" with some Geodata, and here's what I've gotten done today.

## Project Structure

- `landfill.ipynb`: Jupyter notebook containing the analysis code.
- `data/`: Directory containing the necessary data files, including topography data.

## Analysis Steps

1. **Data Collection**:
    - Retrieve the boundary of Tbilisi.
    - Extract districts, landfills, water bodies, waterways, and roads within Tbilisi.

2. **Topography Data**:
    - Load and preprocess topography data.
    - Clip the topography data to the bounding box of the collected features.

3. **Buffer and Spatial Join**:
    - Buffer landfill geometries by 100 meters.
    - Perform a spatial join to find waterways within the buffer.

4. **Elevation Analysis**:
    - Calculate the elevation of points along the waterways.
    - Identify the minimum elevation points and their proximity to landfills.
    - Use elevation data to identify which portions of waterways are downhill from a landfill.

5. **Visualization**:
    - Plot the results using geopandas and matplotlib.

## Visualization

The final visualization shows the waterways within 100 meters of landfills, overlaid on a contour map of Tbilisi's topography. The polluted waterways are highlighted in yellow.

## Requirements

- Python 3.12.6
- Required Python packages: `osmnx`, `geopandas`, `matplotlib`, `rioxarray`, `pandas`, `shapely`

## Reproduction

1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/rivers-of-tbilisi.git
    cd rivers-of-tbilisi
    ```

2. Install the required packages:
    ```bash
    pip install -r requirements.txt
    ```

3. Open the Jupyter notebook:
    ```bash
    jupyter notebook landfill.ipynb
    ```

4. Run the cells in the notebook to perform the analysis and generate the visualization.

## Contact

For any questions or feedback, feel free to reach out to me on [Mastodon](https://defcon.social/@specialprocedures).
