# Banking Simulator

A console-based **Mobile Financial Service (MFS)** simulator written in C — similar in spirit to apps like bKash or Nagad. It supports user login, money transfers, bill payments, transaction history, balance tracking, and a reward-points mini-game system that can be redeemed for cash.

## Features

- **User login system** — username/password authentication
- **Send Money (Local)** — transfer funds to a local phone number with a reference note
- **Send Money (Foreign)** — transfer funds internationally
- **Pay Bills** — bill payment flow
- **Transaction History** — logs every transaction (phone number, amount, reference, resulting balance) to `Transaction History.txt`
- **Balance Check** — view current balance, persisted in `Balance.txt`
- **Play Games to Win Rewards** — mini-games to earn reward points:
  - Tic-Tac-Toe
  - Quiz ("Quizzard")
- **Withdraw Game Points for Cash** — convert earned reward points into account balance
- **Exit** — safely close the program

## How It Works

On startup, the program shows a splash screen and prompts for login. Once authenticated, the user is presented with a menu:

```
1. Send Money (Local)
2. Send Money (Foreign)
3. Pay Bills
4. Transaction History
5. Play games to win rewards
6. Withdraw game points for cash
7. Balance
8. Exit
```

Each option routes to its own function. Balances and transaction history are persisted to local `.txt` files so state carries over between runs.

## Requirements

- A C compiler (e.g., GCC / MinGW on Windows, or Turbo C)
- **Windows only**: the program uses Windows-specific calls (`conio.h`, `system("cls")`, `system("COLOR BC")`, `Sleep()`), so it compiles and runs on Windows out of the box. On Linux/macOS these would need to be adapted (e.g., replacing `conio.h`/`Sleep` with portable equivalents).

## Build & Run

**Windows (MinGW/GCC):**
```bash
gcc PROJECT.c -o mfs_simulator.exe
mfs_simulator.exe
```

**Turbo C / legacy compilers:** open `PROJECT.c` directly and compile/run from the IDE.

## Default Login

- **Username:** `Team01`
- **Password:** `admin01`

> Note: Credentials are hardcoded for demo purposes — this is an academic/learning project, not intended for real financial use.

## Files Generated at Runtime

- `Balance.txt` — current account balance
- `Transaction History.txt` — log of all transactions

## Project Type

Academic C programming project demonstrating file I/O, control flow, functions, and simple console-based UI design.
