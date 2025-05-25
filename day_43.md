# Date = 4 April 2025  
# ADVANCED STREAMLIT FEATURES  

Today, I continued exploring Streamlit to deepen my understanding of building interactive, user-friendly data applications. I focused on advanced widgets, handling user input, file uploads, and integrating media for richer user experiences.

---

## Streamlit Widgets for User Input

Streamlit offers various widgets that enable dynamic input from users:  

- **st.text_input()** — Get text input from users.  
- **st.text_area()** — Multi-line text input.  
- **st.number_input()** — Input numbers with optional min/max values.  
- **st.date_input()** — Date picker widget.  
- **st.time_input()** — Time picker widget.  
- **st.file_uploader()** — Upload files like CSV, images, etc.  
- **st.color_picker()** — Select a color from a palette.  
- **st.multiselect()** — Select multiple options from a list.

---

## Handling File Uploads

File upload is critical for data apps that require user data input. Streamlit makes it simple:

```python
import streamlit as st
import pandas as pd

uploaded_file = st.file_uploader("Choose a CSV file", type="csv")
if uploaded_file is not None:
    df = pd.read_csv(uploaded_file)
    st.write("Data Preview:")
    st.dataframe(df.head())

```
```python
import streamlit as st

st.sidebar.title("Sidebar Menu")
option = st.sidebar.selectbox("Select option:", ['Option 1', 'Option 2'])

col1, col2 = st.columns(2)
col1.write("This is column 1")
col2.write("This is column 2")

with st.expander("See more details"):
    st.write("Hidden content revealed on click.")
```