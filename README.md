# repo-sample
A sample repository for learning GitHub
sample-todo-app/
├── src/
│   ├── __init__.py
│   ├── main.py
│   ├── todo.py
├── tests/
│   ├── __init__.py
│   ├── test_todo.py
├── .gitignore
├── LICENSE
├── README.md
├── requirements.txt
├── setup.py

def main():
    todo_list = TodoList()
    while True:
        print("\n1. Add Task\n2. View Tasks\n3. Complete Task\n4. Exit")
        choice = input("Choose an option: ")
        if choice == "1":
            task = input("Enter task: ")
            todo_list.add_task(task)
        elif choice == "2":
            todo_list.view_tasks()
        elif choice == "3":
            index = int(input("Enter task number to complete: ")) - 1
            todo_list.complete_task(index)
        elif choice == "4":
            break
        else:
            print("Invalid choice.")

if __name__ == "__main__":
    main()

    class TodoList:
    def __init__(self):
        self.tasks = []

    def add_task(self, task):
        self.tasks.append({"task": task, "completed": False})
        print(f"Added task: {task}")

    def view_tasks(self):
        if not self.tasks:
            print("No tasks.")
            return
        for i, task in enumerate(self.tasks, 1):
            status = "✓" if task["completed"] else " "
            print(f"{i}. [{status}] {task['task']}")

    def complete_task(self, index):
        if 0 <= index < len(self.tasks):
            self.tasks[index]["completed"] = True
            print(f"Completed task: {self.tasks[index]['task']}")
        else:
            print("Invalid task number.")
