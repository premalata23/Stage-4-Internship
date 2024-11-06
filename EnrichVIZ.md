 # **EnrichVIZ**
## **Authors ([@slack](https://app.slack.com/client/T07DGMU5S6L/D07K3R60MEE))**

- Dua Gulzar ([@Dua](https://hackbiointern-leo4437.slack.com/team/U07K6A4L18C))
- Premalata Pati ([@Premalata](https://hackbiointern-leo4437.slack.com/team/U07JD8NKQ30))
- Jesse Frank Juma ([@jesse](https://hackbiointern-leo4437.slack.com/team/U07K64WPXU0))
## **App Link:**

To see the app in workng [Click Here](https://enrichviz.shinyapps.io/EnrichVIZ/)

## **Documentation for Using the App**
### **Overview**
The **EnrichVIZ** app allows users to perform functional enrichment analysis, focusing on **Gene Ontology (GO)** terms, biological pathways, and cellular components. The app offers an intuitive and visually appealing interface to explore gene functions and interactions through multiple analysis tabs.
### **Steps to Use the App:**
1. **Launch the App:** Open the app in your browser. You will see the homepage with a welcoming message and a brief introduction to BioLinkR's functionality.

2. **Navigate to the Enrichment Analysis Tab:**
   
   - Click on the "Enrichment Analysis" tab in the navigation bar to perform gene ontology enrichment analysis.
3. **Input Gene Symbols:**

    - In the "Enrichment Parameters" box, enter a list of gene symbols separated by commas. Example: TP53, BRCA1, EGFR.
    - Ensure you input valid gene symbols for accurate analysis.
4. **Run the Analysis:**

    - Click the "Run Enrichment Analysis" button to initiate the analysis.
    - The app will process the gene list and perform enrichment analysis using TCGAanalyze_EAcomplete() from the TCGAbiolinks package.
    - While the analysis is running, a status message will be displayed to indicate progress.
5. **Explore the Results:**

- After the analysis completes, the results will be displayed in four tabs:
    - **Biological Processes:** A barplot visualizing the enriched biological processes, along with a data table showing detailed results.
    - **Molecular Functions:** A barplot and table displaying molecular function enrichment.
    - **Cellular Components:** A barplot and table for cellular components analysis.
    - **Pathways:** A barplot and table presenting enriched biological pathways.

## **Report on App Functionality and Development**
### **Functionality:**
The EnrichVIZ app is designed to facilitate gene ontology enrichment analysis for researchers and bioinformaticians. The app enables users to:

- Input a custom gene list to explore biological processes, molecular functions, cellular components, and pathways related to the genes.
- Visualize enriched gene ontology terms through interactive bar plots.
- Examine detailed results using interactive tables for further interpretation and reporting.
  

The analysis is powered by the **TCGAanalyze_EAcomplete()** function from the **TCGAbiolinks package**, which integrates regulatory and gene expression data. The app processes the gene list inputted by the user, performs the analysis, and presents the findings across multiple GO categories.

### **Methods Used:**
1. **Data Input:**

- Users input comma-separated gene symbols, which are parsed and passed to the TCGAbiolinks enrichment analysis functions.
2. **Enrichment Analysis:**

- The app utilizes **TCGAanalyze_EAcomplete()** to perform functional enrichment analysis on the input gene list.
- The analysis results are categorized into four types:
    - Biological Processes (ResBP)
    - Molecular Functions (ResMF)
    - Cellular Components (ResCC)
    - Pathways
3. **Visualization:**

- For each analysis category, bar plots are generated using **TCGAvisualize_EAbarplot()**.
- Gradient color palettes are applied to distinguish different categories for better visualization.
4. **Interactive Tables:**

- Results are displayed in interactive tables using the **DT package**, allowing users to sort, filter, and download the data.
5. **Challenges Encountered:**
- **Null Values in Dataset:**

    - Initial attempts at using certain TCGA datasets led to issues with null values, requiring adjustments in dataset selection and preprocessing.
- **Responsive Design:**

    - Ensuring the app is visually appealing on different screen sizes posed some challenges. Custom CSS was added to enhance the layout and ensure consistency across devices.
- **Performance Considerations:**

    - Handling large gene lists or complex enrichment analyses can cause delays. To mitigate this, a progress bar was introduced to indicate the analysis status.
- **Customization of Visualizations:**

    - Fine-tuning the plots and tables required custom color palettes and formatting to ensure clarity and user-friendly visualizations.
