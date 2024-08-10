```python
grass_type = pokemon_df[pokemon_df["Type 1"] == "Grass"]
water_type = pokemon_df[pokemon_df["Type 1"] == "Water"]
```
```python
sns.regplot(x="Attack", y="Defense", data=grass_type, color="green", ci=99, marker="o", line_kws={"color":"purple"})
plt.title("Grass type pokemons, Attack vs Defense")
plt.show()
```
```python
sns.regplot(x="Attack", y="Defense", data=water_type, color="blue", ci=99, marker="o", line_kws={"color":"purple"})
plt.title("Water type pokemons, Attack vs Defense")
plt.show()
```
```python
grass_correlation = grass_type['Attack'].corr(grass_type['Defense'])
grass_correlation
```
```python
water_correlation = water_type['Attack'].corr(water_type['Defense'])
water_correlation
```
<img width="595" alt="image" src="https://github.com/user-attachments/assets/b3a0e3f7-51a0-4088-9508-de6919dcd1f0">
<img width="592" alt="image" src="https://github.com/user-attachments/assets/5e2d4dd9-99af-44dc-a100-09fed125e302">







