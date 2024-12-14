# to-do

# A list to store tasks
todo_list = []

def show_menu():
    print("\nTo-Do List Menu:")
    print("1. View Tasks")
    print("2. Add a Task")
    print("3. Remove a Task")
    print("4. Exit")

def view_tasks():
    if not todo_list:
        print("\nYour to-do list is empty!")
    else:
        print("\nYour To-Do List:")
        for i, task in enumerate(todo_list, start=1):
            print(f"{i}. {task}")

def add_task():
    task = input("Enter a new task: ")
    todo_list.append(task)
    print(f"Task '{task}' added to the list!")

def remove_task():
    view_tasks()
    try:
        task_num = int(input("\nEnter the number of the task to remove: "))
        if 1 <= task_num <= len(todo_list):
            removed_task = todo_list.pop(task_num - 1)
            print(f"Task '{removed_task}' removed from the list!")
        else:
            print("Invalid task number!")
    except ValueError:
        print("Please enter a valid number.")

# Main Program Loop
while True:
    show_menu()
    choice = input("\nChoose an option (1-4): ")
    
    if choice == "1":
        view_tasks()
    elif choice == "2":
        add_task()
    elif choice == "3":
        remove_task()
    elif choice == "4":
        print("Exiting To-Do List App. Goodbye!")
        break
    else:
        print("Invalid choice. Please try again!")
