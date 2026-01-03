# contact_book.py

contacts = []

def add_contact():
    print("\n--- Add Contact ---")
    store = input("Store Name: ")
    phone = input("Phone Number: ")
    email = input("Email: ")
    address = input("Address: ")
    contact = {'store_name': store, 'phone': phone, 'email': email, 'address': address}
    contacts.append(contact)
    print("Contact added successfully!")

def view_contacts():
    print("\n--- Contact List ---")
    if not contacts:
        print("No contacts available.")
        return
    for idx, c in enumerate(contacts, 1):
        print(f"{idx}. {c['store_name']} - {c['phone']}")

def search_contact():
    print("\n--- Search Contact ---")
    query = input("Enter name or phone number to search: ").lower()
    found = False
    for c in contacts:
        if query in c['store_name'].lower() or query in c['phone']:
            print(f"{c['store_name']} | {c['phone']} | {c['email']} | {c['address']}")
            found = True
    if not found:
        print("No matching contact found.")

def select_contact():
    view_contacts()
    try:
        num = int(input("Select contact number: "))
        if num < 1 or num > len(contacts):
            print("Invalid number.")
            return None
        return num - 1
    except ValueError:
        print("Enter a valid number.")
        return None

def update_contact():
    print("\n--- Update Contact ---")
    idx = select_contact()
    if idx is None:
        return
    c = contacts[idx]
    print("Press Enter to keep current value.")
    store = input(f"Store Name [{c['store_name']}]: ") or c['store_name']
    phone = input(f"Phone Number [{c['phone']}]: ") or c['phone']
    email = input(f"Email [{c['email']}]: ") or c['email']
    address = input(f"Address [{c['address']}]: ") or c['address']
    contacts[idx] = {'store_name': store, 'phone': phone, 'email': email, 'address': address}
    print("Contact updated successfully!")

def delete_contact():
    print("\n--- Delete Contact ---")
    idx = select_contact()
    if idx is not None:
        deleted = contacts.pop(idx)
        print(f"Deleted: {deleted['store_name']}")

def main_menu():
    while True:
        print("\n==== Contact Book ====")
        print("1. Add Contact")
        print("2. View Contacts")
        print("3. Search Contact")
        print("4. Update Contact")
        print("5. Delete Contact")
        print("6. Exit")
        choice = input("Select option (1-6): ")
        if choice == '1':
            add_contact()
        elif choice == '2':
            view_contacts()
        elif choice == '3':
            search_contact()
        elif choice == '4':
            update_contact()
        elif choice == '5':
            delete_contact()
        elif choice == '6':
            print("Goodbye!")
            break
        else:
            print("Invalid option. Try again.")

if __name__ == '__main__':
    main_menu()
