# Campus Cleaner: A Smart System for Reporting and Managing Dirty Areas 

reports = []
report_id = 1

def student_menu():
    print("\n=== STUDENT MENU ===")
    print("1. Report Dirty Area")
    print("2. View All Reports")
    print("3. Exit")

def admin_menu():
    print("\n=== ADMIN MENU ===")
    print("1. View All Reports")
    print("2. Mark as Cleaned")
    print("3. Delete Report")
    print("4. Exit")

def view_reports():
    if not reports:
        print("No reports yet.")
    else:
        print("\n--- All Reports ---")
        for r in reports:
            print(f"ID: {r['id']} | Location: {r['location']} | Status: {r['status']}")

while True:
    print("\n=== CAMPUS CLEANER CONSOLE ===")
    user_type = input("Select User Type (Student/Admin): ").strip().lower()

    if user_type == "student":
        while True:
            student_menu()
            choice = input("Enter your choice: ")

            if choice == "1":
                location = input("Enter location of dirty area: ")
                reports.append({"id": report_id, "location": location, "status": "Dirty"})
                print(f"Report added! (ID: {report_id})")
                report_id += 1
            elif choice == "2":
                view_reports()
            elif choice == "3":
                print("Exiting Student Menu...")
                break
            else:
                print("Invalid choice. Please try again.")

    if user_type == "admin":
        while True:
            admin_menu()
            choice = input("Enter your choice: ")

            if choice == "1":
                view_reports()
            elif choice == "2":
                try:
                    id_to_clean = int(input("Enter report ID to mark as cleaned: "))
                    found = False
                    for r in reports:
                        if r["id"] == id_to_clean:
                            r["status"] = "Cleaned"
                            print(f"Report ID {id_to_clean} marked as Cleaned.")
                            found = True
                            break
                    if not found:
                        print("Report ID not found.")
                except ValueError:
                    print("Please enter a valid number.")
            elif choice == "3":
                try:
                    id_to_delete = int(input("Enter report ID to delete: "))
                    for r in reports:
                        if r["id"] == id_to_delete:
                            reports.remove(r)
                            print(f"Report ID {id_to_delete} deleted.")
                            break
                    else:
                        print("Report ID not found.")
                except ValueError:
                    print("Please enter a valid number.")
            elif choice == "4":
                print("Exiting Admin Menu...")
                break
            else:
                print("Invalid choice. Please try again.")

    else:
        print("Invalid user type. Please enter 'Student' or 'Admin'.")
