# API Documentation

This document provides a complete reference for the API endpoints available in the bop-maintenance-control project.

## Table of Contents
1. [Equipment CRUD](#equipment-crud)
2. [Maintenance Records](#maintenance-records)
3. [Inspection Groups](#inspection-groups)
4. [RepairKit Tracking](#repairkit-tracking)

## Equipment CRUD

### Create Equipment
- **Endpoint:** `POST /api/equipment`
- **Request Body:**
  ```json
  {
      "name": "Excavator",
      "model": "CAT320",
      "serial_number": "123456789",
      "purchase_date": "2023-01-05"
  }
  ```
- **Response:**
  - **201 Created**
  ```json
  {
      "id": "1",
      "name": "Excavator",
      "model": "CAT320",
      "serial_number": "123456789",
      "purchase_date": "2023-01-05"
  }
  ```

### Read Equipment
- **Endpoint:** `GET /api/equipment/{id}`
- **Response:**
  - **200 OK**
  ```json
  {
      "id": "1",
      "name": "Excavator",
      "model": "CAT320",
      "serial_number": "123456789",
      "purchase_date": "2023-01-05"
  }
  ```

### Update Equipment
- **Endpoint:** `PUT /api/equipment/{id}`
- **Request Body:**
  ```json
  {
      "name": "Excavator",
      "model": "CAT320",
      "serial_number": "987654321",
      "purchase_date": "2023-01-05"
  }
  ```
- **Response:**
  - **200 OK**
  ```json
  {
      "id": "1",
      "name": "Excavator",
      "model": "CAT320",
      "serial_number": "987654321",
      "purchase_date": "2023-01-05"
  }
  ```

### Delete Equipment
- **Endpoint:** `DELETE /api/equipment/{id}`
- **Response:**
  - **204 No Content**

## Maintenance Records

### Create Maintenance Record
- **Endpoint:** `POST /api/maintenance`
- **Request Body:**
  ```json
  {
      "equipment_id": "1",
      "description": "Oil change",
      "date": "2026-04-23",
      "cost": 150.00
  }
  ```
- **Response:**
  - **201 Created**
  ```json
  {
      "id": "1",
      "equipment_id": "1",
      "description": "Oil change",
      "date": "2026-04-23",
      "cost": 150.00
  }
  ```

### Read Maintenance Record
- **Endpoint:** `GET /api/maintenance/{id}`
- **Response:**
  - **200 OK**
  ```json
  {
      "id": "1",
      "equipment_id": "1",
      "description": "Oil change",
      "date": "2026-04-23",
      "cost": 150.00
  }
  ```

### Update Maintenance Record
- **Endpoint:** `PUT /api/maintenance/{id}`
- **Request Body:**
  ```json
  {
      "cost": 200.00
  }
  ```
- **Response:**
  - **200 OK**
  ```json
  {
      "id": "1",
      "equipment_id": "1",
      "description": "Oil change",
      "date": "2026-04-23",
      "cost": 200.00
  }
  ```

### Delete Maintenance Record
- **Endpoint:** `DELETE /api/maintenance/{id}`
- **Response:**
  - **204 No Content**

## Inspection Groups

### Create Inspection Group
- **Endpoint:** `POST /api/inspection-groups`
- **Request Body:**
  ```json
  {
      "name": "Monthly Safety Inspection",
      "description": "Routine safety checks for all equipment"
  }
  ```
- **Response:**
  - **201 Created**
  ```json
  {
      "id": "1",
      "name": "Monthly Safety Inspection",
      "description": "Routine safety checks for all equipment"
  }
  ```

### Read Inspection Group
- **Endpoint:** `GET /api/inspection-groups/{id}`
- **Response:**
  - **200 OK**
  ```json
  {
      "id": "1",
      "name": "Monthly Safety Inspection",
      "description": "Routine safety checks for all equipment"
  }
  ```

### Update Inspection Group
- **Endpoint:** `PUT /api/inspection-groups/{id}`
- **Request Body:**
  ```json
  {
      "description": "Updated description of safety checks"
  }
  ```
- **Response:**
  - **200 OK**
  ```json
  {
      "id": "1",
      "name": "Monthly Safety Inspection",
      "description": "Updated description of safety checks"
  }
  ```

### Delete Inspection Group
- **Endpoint:** `DELETE /api/inspection-groups/{id}`
- **Response:**
  - **204 No Content**

## RepairKit Tracking

### Create RepairKit
- **Endpoint:** `POST /api/repairkits`
- **Request Body:**
  ```json
  {
      "name": "Basic Repair Kit",
      "items": [
          "Wrench",
          "Screwdriver"
      ]
  }
  ```
- **Response:**
  - **201 Created**
  ```json
  {
      "id": "1",
      "name": "Basic Repair Kit",
      "items": [
          "Wrench",
          "Screwdriver"
      ]
  }
  ```

### Read RepairKit
- **Endpoint:** `GET /api/repairkits/{id}`
- **Response:**
  - **200 OK**
  ```json
  {
      "id": "1",
      "name": "Basic Repair Kit",
      "items": [
          "Wrench",
          "Screwdriver"
      ]
  }
  ```

### Update RepairKit
- **Endpoint:** `PUT /api/repairkits/{id}`
- **Request Body:**
  ```json
  {
      "items": [
          "Wrench",
          "Screwdriver",
          "Hammer"
      ]
  }
  ```
- **Response:**
  - **200 OK**
  ```json
  {
      "id": "1",
      "name": "Basic Repair Kit",
      "items": [
          "Wrench",
          "Screwdriver",
          "Hammer"
      ]
  }
  ```

### Delete RepairKit
- **Endpoint:** `DELETE /api/repairkits/{id}`
- **Response:**
  - **204 No Content**