```python
import pandas as pd
import matplotlib.pyplot as plt

dataset = pd.read_csv('/content/transaction_dataset.csv') #reading the file

gender_counts=dataset['Gender'].value_counts(dropna=False)

plt.bar(gender_counts.index.astype(str),gender_counts, color='skyblue')

plt.xlabel('Gender')
plt.ylabel('Count of Transactions')
plt.title('Count of Transactions by Gender')

plt.show()

```

<img width="597" alt="image" src="https://github.com/user-attachments/assets/e27db84f-7b76-4a44-9a84-eb83fe61f4ea">
