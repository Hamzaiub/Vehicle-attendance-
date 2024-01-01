hafiz Hamza
BSEEN1E02021
class Vehicle:
    def __init__(self, vehicle_id, driver_name):
        self.vehicle_id = vehicle_id
        self.driver_name = driver_name
        self.attendance_status = False

    def mark_attendance(self):
        self.attendance_status = True
        print(f"Attendance marked for {self.driver_name} ({self.vehicle_id})")

    def display_info(self):
        print(f"Vehicle ID: {self.vehicle_id}")
        print(f"Driver Name: {self.driver_name}")
        print(f"Attendance Status: {'Present' if self.attendance_status else 'Absent'}")


class VehicleAttendanceTracker:
    def __init__(self):
        self.vehicles = []

    def add_vehicle(self, vehicle):
        self.vehicles.append(vehicle)

    def mark_attendance_by_id(self, vehicle_id):
        for vehicle in self.vehicles:
            if vehicle.vehicle_id == vehicle_id:
                vehicle.mark_attendance()
                return
        print(f"Vehicle with ID {vehicle_id} not found.")

    def display_all_vehicles_info(self):
        for vehicle in self.vehicles:
            vehicle.display_info()
            print("---------------------")


# Example usage:
vehicle1 = Vehicle(vehicle_id="ABC123", driver_name="John Doe")
vehicle2 = Vehicle(vehicle_id="XYZ456", driver_name="Jane Smith")

attendance_tracker = VehicleAttendanceTracker()
attendance_tracker.add_vehicle(vehicle1)
attendance_tracker.add_vehicle(vehicle2)

attendance_tracker.mark_attendance_by_id("ABC123")

attendance_tracker.display_all_vehicles_info()
