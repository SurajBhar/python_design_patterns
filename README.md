# Low-Level Design in Python

This repository is a Python LLD practice bank that combines OOP fundamentals, UML relationships, SOLID principles, classic design patterns, a ride-sharing case study, and 50 standalone low-level design problems.

## Current Scope

- 23 top-level numbered content directories
- 147 Python files, excluding `__pycache__`
- 50 standalone files under `50. LLD Problems/`
- 1 PDF reference document in `50. LLD Problems/`
- No packaged application, test suite, or `pyproject.toml`; examples are meant to be run file by file

## What The Repository Contains

### Foundations

- `1. OOPS Recap`: classes, objects, inheritance, abstraction, encapsulation, and a small movie-booking exercise
- `1. OOPS Recap/2. UML Basics`: association, aggregation, composition, inheritance, and dependency
- `2. SOLID Principles`: bad and good examples for SRP, OCP, LSP, ISP, and DIP

### Design Patterns

- Behavioral: Memento, Observer, Strategy, Command, Template, Iterator, State, Mediator
- Creational: Singleton, Factory, Abstract Factory, Builder, Prototype
- Structural: Adapter, Decorator, Proxy, Composite, Facade

### LLD Case Study

- `21. Ride Sharing Project - Bad Example`: tightly coupled version
- `22. Ride Sharing Project - Good Example`: abstraction-driven version with users, vehicles, fare strategies, rides, and ride matching

### 50 LLD Problems

The `50. LLD Problems` directory contains 50 single-file implementations covering:

- Infrastructure and platform topics such as rate limiting, load balancing, logging, URL shortening, distributed locking, caching, circuit breaking, job queues, code compilation, feature flags, configuration management, and geo-location
- Product and business topics such as parking lots, ATMs, notifications, payment gateways, authentication, MFA, shopping carts, reviews, booking systems, coupons, auctions, inventory, loyalty, subscriptions, workflows, and bulk imports
- Interactive and simulation-style topics such as vending machines, traffic control, chess, elevator systems, text editing, undo/redo, and Tic-Tac-Toe

## Requirements

- Python 3.10+ is recommended
- The current workspace validation was done with `Python 3.12.7`
- Most files use only the Python standard library
- The only current third-party dependency is `cryptography`, used by `50. LLD Problems/26.DesignAPasswordVaultSystem.py`

## Setup

### Option 1: Standard Python Virtual Environment

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

### Option 2: `uv`

```bash
uv venv .venv
source .venv/bin/activate
uv pip install -r requirements.txt
```

## Running Examples

This repository is not a Python package. Run files directly and quote paths that contain spaces.

```bash
python "4. Observer Pattern/main.py"
python "6. Command Pattern/main.py"
python "22. Ride Sharing Project - Bad Example/client.py"
python "50. LLD Problems/18.DesignAGenericNotificationSystem.py"
python "50. LLD Problems/49.DesignAConfigurationManager.py"
```

Some files are intentionally interactive:

```bash
python "50. LLD Problems/07.DesignAVendingMachine.py"
python "50. LLD Problems/10.DesignChessGame.py"
python "50. LLD Problems/25.DesignAMulti-FactorAuthentication(MFA)System.py"
```

## Current Execution Snapshot

Based on the latest repository scan:

- 128 Python files run successfully as-is
- 14 files fail under unattended execution
- 5 files exceed a 5-second automated execution window

### Intentional Teaching Failures

- `2. SOLID Principles/3. Liskov Substitution Principle (LSP)/1. Bad Example/1. bad_example.py`
- `2. SOLID Principles/4. Interface Segregation Principle (ISP)/1. bad_example.py`

These are expected because they demonstrate broken designs.

### Interactive Or Long-Running Demos

- Interactive stdin-driven demos:
  - `50. LLD Problems/07.DesignAVendingMachine.py`
  - `50. LLD Problems/10.DesignChessGame.py`
  - `50. LLD Problems/25.DesignAMulti-FactorAuthentication(MFA)System.py`
- Long-running demos:
  - `50. LLD Problems/08.DesignATrafficControlSystem.py`
  - `50. LLD Problems/11.DesignAnElevatorSystem.py`
  - `50. LLD Problems/16.DesignDistributedLockManager(DLM).py`
  - `50. LLD Problems/32.DesignAuctionSystem.py`
  - `50. LLD Problems/39.DesignACircuitBreakerSystem.py`

### Known Implementation Issues

- `1. OOPS Recap/1. Revision/enacapsulation.py` calls a name-mangled private method directly
- `21. Ride Sharing Project - Bad Example/client.py` depends on a missing `__calcDistance` implementation
- `22. Ride Sharing Project - Good Example/` is partially blocked by the `Location` type-annotation/import issue in `location.py`, which affects the dependent modules in that directory

## Notes

- Filenames and directories intentionally preserve the course structure, even where names contain spaces or inconsistent spellings
- `requirements.txt` is intentionally minimal because almost the entire repository is standard-library-only
