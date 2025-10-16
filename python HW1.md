```python

"""
Program: Pet Daycare Management System
Author: [Your Name]
Course: CMPS 4143 - Python Programming
Description: This program manages pet information for a daycare.
             Users can add pets, view all pets, update pet information,
             search pets by species, and exit. Data is stored in a
             list of dictionaries.
"""

# Function to add a new pet
def add_pet(pets):
    print("\n--- Add a New Pet ---\n")
    name = input("Name: ").strip()           # Get pet name
    species = input("Species: ").strip()     # Get pet species
    preference = input("Preference: ").strip()  # Get pet preference
    pets.append({'name': name, 'species': species, 'preference': preference})
    print(f"Details for {name} added.\n")
    print("---------------------------------\n")

# Function to view all pets
def view_pets(pets):
    print("\n--- Showing All Pets List ---\n")
    if not pets:
        print("No pets available.\n")
    else:
        for i, pet in enumerate(pets, start=1):
            # Display all pet info
            print(f"{i}. Name: {pet['name']}, Species: {pet['species']}, Preference: {pet['preference']}")
    print("---------------------------------\n")

# Function to update pet information
def update_pet(pets):
    print("\n--- Update Pet Information ---\n")
    name = input("Name to update: ").strip()
    updated_count = 0
    for pet in pets:
        if pet['name'].lower() == name.lower():
            # Ask for new info (leave blank to keep existing)
            new_name = input("New name: ").strip()
            new_species = input("New species: ").strip()
            new_pref = input("New preference: ").strip()

            if new_name:
                pet['name'] = new_name
            if new_species:
                pet['species'] = new_species
            if new_pref:
                pet['preference'] = new_pref

            updated_count += 1

    if updated_count == 0:
        print(f"No pet named '{name}' found.\n")
    else:
        print(f"{updated_count} pet(s) updated.\n")
    print("---------------------------------\n")

# Function to search pets by species
def search_pets(pets):
    print("\n--- Search Pets by Species ---\n")
    species = input("Species to search: ").strip()
    found = [pet for pet in pets if pet['species'].lower() == species.lower()]
    if not found:
        print(f"No pets of species '{species}' found.\n")
    else:
        for i, pet in enumerate(found, start=1):
            print(f"{i}. Name: {pet['name']}, Preference: {pet['preference']}")
    print("---------------------------------\n")    

# Main program function
def main():
    pets = []           # Initialize empty pet list
    choice = ''
    while choice != '5':   # Loop until user chooses Exit
        print("Please choose an option:")
        print("1. Add new pet")
        print("2. View all pets")
        print("3. Update pet preferences")
        print("4. Search pets by species")
        print("5. Exit")
        choice = input("Enter your choice: ").strip()

        if choice == '1':
            add_pet(pets)
        elif choice == '2':
            view_pets(pets)
        elif choice == '3':
            update_pet(pets)
        elif choice == '4':
            search_pets(pets)
        elif choice == '5':
            print("\nExiting program. Goodbye!\n")
        else:
            print("\nInvalid choice! Enter a number 1-5.\n")
            print("---------------------------------\n")

# Run the program
if __name__ == "__main__":
    main()

```
