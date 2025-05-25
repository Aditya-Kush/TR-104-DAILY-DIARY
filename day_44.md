# Date = 7 April 2025  
# STREAMLIT INTERACTIVITY & DEPLOYMENT  

Today, I expanded my knowledge of Streamlit by exploring interactive app features, managing app state, and learning the basics of deploying Streamlit apps for sharing with others.

---

## Interactive Widgets & Callbacks

Streamlit apps run top-to-bottom on every user interaction, but widgets allow you to create dynamic behavior. Some key points:  

- Widgets like sliders, buttons, and text inputs automatically trigger reruns.  
- You can use widget return values to conditionally display content or perform calculations.  
- Use `st.form` to batch multiple inputs and submit together for better control.

Example with a button triggering an action:

```python
import streamlit as st

if st.button('Click me'):
    st.write("Button clicked!")
else:
    st.write("Button not clicked yet.")
```

```python
import streamlit as st

if 'count' not in st.session_state:
    st.session_state.count = 0

increment = st.button('Increment')

if increment:
    st.session_state.count += 1

st.write(f"Counter value: {st.session_state.count}")
```

```python
import streamlit as st

with st.form(key='my_form'):
    name = st.text_input('Enter your name')
    age = st.number_input('Enter your age', min_value=0)
    submit_button = st.form_submit_button(label='Submit')

if submit_button:
    st.write(f'Hello {name}, you are {age} years old.')
