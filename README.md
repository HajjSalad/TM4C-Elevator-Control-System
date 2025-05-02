## 🛗 Elevator Control System

This project implements a task-based elevator control system using FreeRTOS on the TM4C123GXL LaunchPad. The system demonstrates real-time operating system concepts through a practical application.

#### 🔑 Features
- **Request Handling:** User input for floor requests is captured via SW1 (floor selection) and SW2 (confirmation), ensuring accurate request processing.
- **Elevator Control:** Manages elevator movement based on user requests, determining direction and operation to reach the selected floor.
- **Display Updates:** Real-time updates on the terminal show the elevator’s current floor, movement direction, and status.
- **Log System:** Logs system events, such as floor requests and elevator movements, for debugging and monitoring.

#### 🔧 FreeRTOS Implementation
📌 **Tasks Structure**  
1. **InputTask:** Captures user floor requests by reading SW1 for floor selection and SW2 for confirmation, passing the input to the elevator control system.
2. **DisplayTask:** Continuously updates the terminal with the current floor, elevator status, and movement direction for real-time feedback.
3. **LogTask:** Logs system activities, such as floor requests and elevator movements, into a circular buffer for monitoring and debugging.
4. **LogProcessorTask:** Processes the logged data, reading it from the circular buffer and displaying it on the terminal for the user to view.

📡 **Inter-Task Communication**  
**Queues** - Facilitates inter-task communication.    
&nbsp;&nbsp;&nbsp;&nbsp;• Example: `xDisplayQueue`: Sends display updates to DisplayTask     
**Semaphores** - Ensures mutual exclusion.     
&nbsp;&nbsp;&nbsp;&nbsp;• Example: `xUARTSemaphore`: Protects UART access for display output     
**Task Notifications** - Used for lightweight signaling between tasks      
&nbsp;&nbsp;&nbsp;&nbsp;• Example: DisplayTask notifies LogTask when important events occur     
   
#### ⚙️ Tools and Software
- Code Composer Studio
- TM4C123GXL Launchpad
- TivaWare for C Series Software

#### 📺 Demo   
View the demo in action. ![Elevator Control Demo](./freertos_elev_demo.gif) 
