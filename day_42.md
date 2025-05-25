# Date = 3 April 2025  
# PYTHON LIBRARIES  

Today, I focused on understanding how to build interactive data applications in Python using the `streamlit` library. Streamlit allows for quick development of web apps for data visualization, machine learning model deployment, and rapid prototyping without requiring front-end web development skills.

---

# Introduction to Streamlit  
`Streamlit` is an open-source Python library that enables data scientists and developers to create beautiful, interactive, and shareable web apps in pure Python. It abstracts away the complexities of web development and lets users focus on the data and logic.

Key features include:  
1. Easy and fast to learn and use.  
2. Automatic UI generation from Python scripts.  
3. Built-in widgets for interactivity (buttons, sliders, dropdowns).  
4. Supports live updates and real-time data visualization.  
5. Seamless integration with popular data science libraries like pandas, matplotlib, Plotly, and scikit-learn.

---

## How Streamlit Works

- Write a Python script that contains your data processing, visualization, and UI widgets.  
- Run the script with `streamlit run script_name.py`.  
- Streamlit creates a web app that updates automatically when you change the script.  
- The app can be shared locally or deployed on cloud platforms.

---

## Common Streamlit Widgets

1. `st.button()`: Creates a clickable button.  
2. `st.slider()`: Slider to select numeric values.  
3. `st.selectbox()`: Dropdown menu for selecting options.  
4. `st.text_input()`: Input box for text.  
5. `st.checkbox()`: Checkbox toggle.  
6. `st.write()`: Writes text, dataframes, or plots to the app.

---

## Simple Streamlit Example: Displaying Text and Data

```python
import streamlit as st
import pandas as pd
import numpy as np

st.title('My First Streamlit App')

st.write("Here's a simple dataframe:")

df = pd.DataFrame({
    'Column A': np.random.randn(5),
    'Column B': np.random.rand(5)
})

st.write(df)

if st.button('Say hello'):
    st.write('Hello there!')

slider_val = st.slider('Select a value', 0, 100, 25)
st.write('You selected:', slider_val)
