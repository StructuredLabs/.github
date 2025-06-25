<p align="center">
  <img src="./profile/Banner.png" alt="Logo">
</p>

# **Structured Labs Coding Assessment Guide**

---

## [⭐ Step 0: Show some support! Star Preswald on GitHub](https://github.com/StructuredLabs/preswald)

## https://github.com/StructuredLabs/preswald

---
## 📦 1. Setup Environment

* Please use Google Chrome to complete this assessment.

1. **Install Preswald CLI**
   ```bash
   pip install preswald
   ```

2. **Create a new project**
   ```bash
   preswald init my_assessment_app
   cd my_assessment_app
   ```

3. **Start the development server**
   ```bash
   preswald run
   ```

4. **Open your browser** to the local URL shown in the terminal (typically `http://localhost:8000`)

---

### **2. Choose a Dataset**

Select/download a dataset from any of these sources:

- [Kaggle Datasets](https://www.kaggle.com/datasets)
- [Data.gov](https://www.data.gov/)
- [Open Data Repositories](https://github.com/awesomedata/awesome-public-datasets)
- Any CSV file (e.g., weather, finance, sports stats)

Place your dataset in the `data/` folder of your project and update the `preswald.toml` configuration file to reference it.

---

### **3. Implement Your Preswald App**

Modify `hello.py` to include the following:

1. **Load the dataset**
        
    ```python
    from preswald import connect, get_df
        
    connect()  # Initialize connection to preswald.toml data sources
    df = get_df("my_dataset")  # Load data
    ```

2. **Query or manipulate the data**
            
    ```python
    from preswald import query
        
    sql = "SELECT * FROM my_dataset WHERE value > 50"
    filtered_df = query(sql, "my_dataset")
    ```

3. **Build an interactive UI**

    ```python
    from preswald import table, text
    
    text("# My Data Analysis App")
    table(filtered_df, title="Filtered Data")
    ```

    - Add user controls:

    ```python
    from preswald import slider, view
    threshold = slider("Threshold", min_val=0, max_val=100, default=50)
    table(df[df["value"] > threshold], title="Dynamic Data View")
    ```

4. **Create a visualization**

    ```python
    from preswald import plotly
    import plotly.express as px
    
    fig = px.scatter(df, x="column1", y="column2", color="category")
    plotly(fig)
    ```

### 🔹 Add Other Widgets

Add other widgets to your app. Reference the docs here: [Preswald SDK](https://docs.preswald.com/)

---

## 👀 4. Preview Your App

Your app will automatically reload in the browser as you make changes to `hello.py`. The development server provides live preview functionality.

---

## 🚀 5. Export and Deploy Your App

**Export your app as a static site**
   ```bash
   preswald export
   ```


---

## 🎁 (Bonus) Contribute to Preswald OSS!

👉 Check out our [open GitHub issues](https://github.com/StructuredLabs/preswald/issues?q=is%3Aissue+is%3Aopen) and submit a PR to the core Preswald framework.

Pick one, fork the repo, build the solution, and open a pull request. [Contributing Guide](https://github.com/StructuredLabs/preswald/blob/main/CONTRIBUTING.md)

---

## [📤 Submit your finished app code ➡️](https://forms.gle/ATZKNXkCZMruMM1t8) 
