-- User Table
CREATE TABLE User (
  user_id INT AUTO_INCREMENT PRIMARY KEY,
  hasUsername VARCHAR(255) NOT NULL,
  hasEmail VARCHAR(255) NOT NULL
);

-- RentingService Table
CREATE TABLE RentingService (
  renting_service_id INT AUTO_INCREMENT PRIMARY KEY,
  hasName VARCHAR(255) NOT NULL
);

-- Vehicle Table
CREATE TABLE Vehicle (
  vehicle_id INT AUTO_INCREMENT PRIMARY KEY,
  hasModel VARCHAR(255) NOT NULL,
  hasLicensePlate VARCHAR(255) NOT NULL,
  renting_service_id INT NOT NULL,
  FOREIGN KEY (renting_service_id) REFERENCES RentingService(renting_service_id)
);

-- RentingPlan Table
CREATE TABLE RentingPlan (
  renting_plan_id INT AUTO_INCREMENT PRIMARY KEY,
  hasPlanType VARCHAR(255) NOT NULL,
  hasFixedPrice FLOAT NOT NULL,
  hasRidingCostPerKm FLOAT NOT NULL,
  hasRidingCostPerMinute FLOAT NOT NULL,
  hasParkingCostPerMinute FLOAT NOT NULL,
  hasIncludedKm INT NOT NULL,
  hasUnlockFee FLOAT NOT NULL,
  renting_service_id INT NOT NULL,
  FOREIGN KEY (renting_service_id) REFERENCES RentingService(renting_service_id)
);

-- Solution Table
CREATE TABLE Solution (
  solution_id INT AUTO_INCREMENT PRIMARY KEY
);

-- RentingCost Table
CREATE TABLE RentingCost (
  renting_cost_id INT AUTO_INCREMENT PRIMARY KEY,
  hasTotalCost FLOAT NOT NULL,
  renting_plan_id INT NOT NULL,
  trip_id INT NOT NULL,
  FOREIGN KEY (renting_plan_id) REFERENCES RentingPlan(renting_plan_id),
  FOREIGN KEY (trip_id) REFERENCES Trip(trip_id)
);

-- Trip Table
CREATE TABLE Trip (
  trip_id INT AUTO_INCREMENT PRIMARY KEY,
  hasStartLocation VARCHAR(255) NOT NULL,
  hasEndLocation VARCHAR(255) NOT NULL,
  hasStartTime DATETIME NOT NULL,
  hasEndTime DATETIME NOT NULL,
  user_id INT NOT NULL,
  FOREIGN KEY (user_id) REFERENCES User(user_id)
);
