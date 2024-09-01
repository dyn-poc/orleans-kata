# Orleans Best Practices Kata
https://github.com/eebergman/evercraft

Welcome to the Orleans Best Practices Kata! This kata is designed to teach you the best practices in Microsoft Orleans using a collaborative, interactive approach. You'll be implementing parts of an Evercraft RPG game and see how your solutions perform in a shared arena.

## Objectives

- **Understand** when to use stateless versus stateful grains.
- **Learn** how to use `oneway` calls effectively.
- **Master** grain sequence control to ensure correct operation order.
- **Explore** failure handling and retries in a distributed system.
- **Compete** with other participants by uploading your implementations and seeing them perform in a shared arena.

## How It Works

1. **Fork the Repository**: Start by forking this repository to your own GitHub account.
2. **Implement Your Grains**: Follow the instructions in the `/src/Participants` directory to implement your version of the required grains.
3. **Submit a Pull Request**: Once your implementation is ready, submit a pull request to this repository. Your grain will be reviewed and merged into the main branch.
4. **Battle in the Arena**: After merging, your grain will participate in automated battles within the arena. Results will be displayed on the dashboard.
5. **Iterate and Improve**: Analyze your grain's performance, make improvements, and resubmit!

## Repository Structure

- **/arena**: Contains the `ArenaGrain` and related code for managing and orchestrating the battles.
- **/src/Participants**: The directory where you will add your grain implementation. Each participant should create a subdirectory with their grain code.
- **/src/Interfaces**: Contains the common interfaces that all participant grains must implement.
- **/src/Tests**: Unit tests to validate your grain implementations.
- **/dashboard**: A simple web project to display battle results and participant performance.

## Getting Started

### Clone the Repository:
```bash
   git clone https://github.com/yourusername/orleans-best-practices-kata.git
```

### Navigate to the Participants Directory:
```bash
cd src/Participants
```

### Create Your Grain
Implement the required interfaces and add your grain to the appropriate subdirectory.

### Test Locally
Run the provided tests to ensure your grain works correctly.

### Submit Your Work
Push your changes and create a pull request to have your grain included in the arena.


## Grain Implementation Guide
1. **Stateless vs. Stateful Grains**
   **Objective:** Implement grains for combat calculations and character management, deciding which should be stateless and which should be stateful.
2. **Oneway Calls**
   **Objective:** Implement grains that use oneway calls to optimize performance in a battle scenario.
3. **Grain Sequence Control**
   **Objective:** Ensure that operations in a quest sequence happen in the correct order using grain communication.
4. **Failure Handling**
   **Objective:** Implement grains that can handle failures and retries gracefully.


## Arena and Battle System
The ArenaGrain orchestrates battles between participants' grains. Each participant's grain must implement the IArenaParticipantGrain interface to be eligible to compete. The battle results are recorded and displayed on the dashboard.

## Dashboard
The dashboard provides a real-time view of the battle results, including leaderboards and detailed logs. It allows participants to see how their implementations perform against others.

## Contribution Guidelines
Adhere to the common interfaces provided in the /src/Interfaces directory.
Ensure your grain implementation is robust and follows best practices.
Be creative and competitive – the arena is your playground!
 
 