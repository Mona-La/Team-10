```python
#How many Pokémons are with 'Type 1' == Water as a % of total?

all_type1 = len(pokemon_df['Type 1'])
print(all_type1)

water_type1 = len(pokemon_df[pokemon_df['Type 1'] == 'Water'])
print(water_type1)

water_type1_percentage = (water_type1 / all_type1) * 100
print(f"Percentage of Water type Pokémon: {water_type1_percentage:.2f}%")

water_of_total = (len(pokemon_df[pokemon_df['Type 1'] == 'Water'])) / (len(pokemon_df['Type 1']))* 100
print(water_of_total)

# What is the maximum 'Speed' value? What is the minimum 'Speed' value? What is the difference between max and min 'Speed'?

max_speed = pokemon_df['Speed'].max()
print(f'The max Speed value is : {max_speed}')

min_speed = pokemon_df['Speed'].min()
print(f'The min Speed value is : {min_speed}')

difference_speed = (max_speed) - (min_speed)
print(f'Difference between max and min Speed is: {difference_speed}')

speed_eqgt_80 = pokemon_df[pokemon_df['Speed'] >= 80]
print(f'Pokemon with speed equal or greater that 80: {len(speed_eqgt_80)}')


plt.hist(speed_eqgt_80['Speed'], bins = 6, color='red', edgecolor='black', alpha=0.7)

plt.xlabel('Speed')
plt.ylabel('Number of pokemons (Frequency)')
plt.title('Histogram of Pokémon Speeds (>= 80)')
plt.grid(axis='y', linestyle='--', alpha=0.7)

plt.show()
```
<img width="615" alt="image" src="https://github.com/user-attachments/assets/cf284fda-60a4-48ba-96be-70a18b1d86fd">

