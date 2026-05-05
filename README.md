total_seats = 5
booked_tickets = {}

def check_availability():
    print("Available seats:", total_seats - len(booked_tickets))

def book_ticket():
    if len(booked_tickets) >= total_seats:
        print("No seats available!")
        return
    
    name = input("Enter name: ")
    age = input("Enter age: ")
    
    booking_id = len(booked_tickets) + 1
    booked_tickets[booking_id] = {"name": name, "age": age}
    
    print("Ticket booked successfully!")
    print("Your Booking ID:", booking_id)

def view_ticket():
    booking_id = int(input("Enter Booking ID: "))
    if booking_id in booked_tickets:
        print(booked_tickets[booking_id])
    else:
        print("Ticket not found")

def cancel_ticket():
    booking_id = int(input("Enter Booking ID to cancel: "))
    if booking_id in booked_tickets:
        del booked_tickets[booking_id]
        print("Ticket cancelled")
    else:
        print("Invalid ID")

while True:
    print("\n--- Railway Reservation System ---")
    print("1. Check Availability")
    print("2. Book Ticket")
    print("3. View Ticket")
    print("4. Cancel Ticket")
    print("5. Exit")
    
    choice = input("Enter choice: ")
    
    if choice == "1":
        check_availability()
    elif choice == "2":
        book_ticket()
    elif choice == "3":
        view_ticket()
    elif choice == "4":
        cancel_ticket()
    elif choice == "5":
        print("Thank you!")
        break
    else:
        print("Invalid choice")
