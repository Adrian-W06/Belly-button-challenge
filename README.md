# Belly-button-challenge
Module 14
# Bacteria Dashboard JavaScript Application


## Code Structure

### 1. `buildMetadata(sample)`
- **Purpose**: Builds the demographic metadata panel for the selected sample.
- **Location**: Top of the file.
- **Key Operations**:
  - Filters metadata for the selected sample.
  - Selects the `#sample-metadata` panel in the HTML.
  - Clears existing content.
  - Appends key-value pairs from the metadata.

### 2. `buildCharts(sample)`
- **Purpose**: Builds a Bubble Chart and a Bar Chart for the selected sample.
- **Location**: After `buildMetadata()`.
- **Key Operations**:
  - Filters the `samples` array to match the selected sample.
  - Extracts `otu_ids`, `otu_labels`, and `sample_values`.
  - **Bubble Chart**:
    - Renders all data points.
    - Uses `otu_ids` for x-axis and color.
    - Uses `sample_values` for y-axis and marker size.
  - **Bar Chart**:
    - Displays the top 10 OTUs.
    - Renders a horizontal bar chart.

### 3. `init()`
- **Purpose**: Initializes the dashboard on page load.
- **Location**: Toward the end of the file.
- **Key Operations**:
  - Populates the dropdown menu with sample IDs.
  - Calls `buildCharts()` and `buildMetadata()` with the first sample.

### 4. `optionChanged(newSample)`
- **Purpose**: Updates charts and metadata when a new sample is selected from the dropdown.
- **Location**: Just before `init()` is called.
- **Key Operations**:
  - Re-invokes `buildCharts()` and `buildMetadata()` using the newly selected sample.

### 5. `init()`
- **Purpose**: Called at the very end to kick off the dashboard setup.

---

## Technologies Used
- **D3.js**: For data loading and DOM manipulation.
- **Plotly.js**: For chart rendering (Bubble Chart and Bar Chart).
- **JavaScript (ES6)**: Core scripting.
- **HTML/CSS**: For embedding the visual components.

---

## Usage
1. Open the corresponding HTML file in a browser.
2. The dropdown will automatically populate with sample IDs.
3. Selecting a sample updates the metadata and charts.
