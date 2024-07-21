to_do_list = []

print("Simple To-Do List")
print("1. Create To-Do List")
print("2. Update To-Do List")
print("3. View To-Do List")
print("4. Exit")

while True:
    choice = input("\nEnter your choice (1/2/3/4): ")

    if choice == '1':
        to_do_list = []
        print("Enter tasks (type 'q' to stop):")
        while True:
            task = input("Task: ")
            if task.lower() == 'q':
                break
            to_do_list.append(task)

    elif choice == '2':
        if to_do_list:
            print("Current tasks:")
            for i, task in enumerate(to_do_list, 1):
                print(f"{i}. {task}")
            task_num = int(input("Enter task number to update: ")) - 1
            if 0 <= task_num < len(to_do_list):
                new_task = input("Enter new task: ")
                to_do_list[task_num] = new_task
                print("Task updated.")
            else:
                print("Invalid task number.")
        else:
            print("To-do list is empty.")

    elif choice == '3':
        if to_do_list:
            print("To-Do List:")
            for i, task in enumerate(to_do_list, 1):
                print(f"{i}. {task}")
        else:
            print("No tasks in the to-do list.")

    elif choice == '4':
        print("Exiting the To-Do List.")
        break

    else:
        print("Invalid choice, please try again.")
