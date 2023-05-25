import math

def load_previous_result():
    try:
        with open('previous_result.txt', 'r') as file:
            return float(file.read())
    except (FileNotFoundError, ValueError):
        return None


def save_result(result):
    with open('previous_result.txt', 'w') as file:
        file.write(str(result))

def collatz_sequence(number):
    sequence = [number]
    while number != 1:
        if number % 2 == 0:
            number = number // 2
        else:
            number = 3 * number + 1
        sequence.append(number)
    return sequence

def physics_solver():
    previous_result = load_previous_result()
    while True:
        subproblem_type = input("What basic problem do you want me to solve (speed, acceleration, force, energy, work, kinetic energy, momentum, gravitational potential energy) or 'back' to go back: ")
        if subproblem_type == "back":
            break
        if subproblem_type == "speed":
            distance = float(input("Enter the distance (meters): "))
            time = float(input("Enter the time (seconds): "))
            result = calculate_speed(distance, time)
            print(f"The speed is {result:.2f} m/s")
            save_result(result)
        elif subproblem_type == "acceleration":
            initial_velocity = float(input("Enter the initial velocity (m/s): "))
            final_velocity = float(input("Enter the final velocity (m/s): "))
            time = float(input("Enter the time (seconds): "))
            result = calculate_acceleration(initial_velocity, final_velocity, time)
            print(f"The acceleration is {result:.2f} m/s^2")
            save_result(result)
        elif subproblem_type == "force":
            mass = float(input("Enter the mass (kilograms): "))
            acceleration = float(input("Enter the acceleration (m/s^2): "))
            result = calculate_force(mass, acceleration)
            print(f"The force is {result:.2f} N")
            save_result(result)
        elif subproblem_type == "energy":
            mass = float(input("Enter the mass (kilograms): "))
            height = float(input("Enter the height (meters): "))
            result = calculate_energy(mass, height)
            print(f"The potential energy is {result:.2f} J")
            save_result(result)
        elif subproblem_type == "work":
            force = float(input("Enter the force (newtons): "))
            distance = float(input("Enter the distance (meters): "))
            result = calculate_work(force, distance)
            print(f"The work done is {result:.2f} J")
            save_result(result)
        elif subproblem_type == "kinetic energy":
            mass = float(input("Enter the mass (kilograms): "))
            velocity = float(input("Enter the velocity (m/s): "))
            result = calculate_kinetic_energy(mass, velocity)
            print(f"The kinetic energy is {result:.2f} J")
            save_result(result)
        elif subproblem_type == "momentum":
            mass = float(input("Enter the mass (kilograms): "))
            velocity = float(input("Enter the velocity (m/s): "))
            result = calculate_momentum(mass, velocity)
            print(f"The momentum is {result:.2f} kg m/s")
            save_result(result)
        elif subproblem_type == "gravitational potential energy":
            mass = float(input("Enter the mass (kilograms): "))
            height = float(input("Enter the height (meters): "))
            result = calculate_gravitational_potential_energy(mass, height)
            print(f"The gravitational potential energy is {result:.2f} J")
            save_result(result)
        else:
            print("Invalid physics subproblem")

def math_solver():
    previous_result = load_previous_result()
    while True:
        expr = input("Enter a mathematical expression or 'back' to go back: ")
        if expr == "back":
            break
        try:
            result = evaluate_expression(expr)
            print("The result is:", result)
            save_result(result)
        except:
            print("Invalid input")

def evaluate_expression(expression):
    previous_result = load_previous_result()
    allowed_functions = {
        'sin': math.sin,
        'cos': math.cos,
        'tan': math.tan,
        'log': math.log,
        'sqrt': math.sqrt,
        'pi': math.pi,
        'e': math.e,
        'asin': math.asin,
        'acos': math.acos,
        'atan': math.atan,
        'sinh': math.sinh,
        'cosh': math.cosh,
        'tanh': math.tanh,
        'asinh': math.asinh,
        'acosh': math.acosh,
        'atanh': math.atanh,
        'hyp': math.hypot,
        'tau': math.tau,
        'degree': math.degrees,
        'radian': math.radians,
        'ans': previous_result,
    }
    try:
        result = eval(expression, {'__builtins__': None}, allowed_functions)
        save_result(result)
        return result
    except:
        return "Invalid Expression"

def even_odd(num):
    if num % 2 == 0:
        return num // 2
    else:
        return num * 3 + 1

def calculate_speed(distance, time):
    speed = distance / time
    return speed

def calculate_acceleration(initial_velocity, final_velocity, time):
    acceleration = (final_velocity - initial_velocity) / time
    return acceleration

def calculate_force(mass, acceleration):
    force = mass * acceleration
    return force

def calculate_energy(mass, height):
    energy = mass * 9.81 * height
    return energy

def calculate_work(force, distance):
    work = force * distance
    return work

def calculate_kinetic_energy(mass, velocity):
    energy = 0.5 * mass * velocity ** 2
    return energy

def calculate_momentum(mass, velocity):
    momentum = mass * velocity
    return momentum

def calculate_gravitational_potential_energy(mass, height):
    energy = mass * 9.81 * height
    return energy

problem_type = None  

while True:
    if problem_type is None:
        problem_type = input("How do you want me to be your slave today (collatz, physics, math) or 'exit' to quit: ")

    if problem_type == "exit":
        break
    elif problem_type == "collatz":
        num_input = input("Enter a number or 'stop' to stop: ")
        try:
            num = int(num_input)
        except ValueError:
            print("Invalid input. Please enter a valid number.")
            continue
        while num != 1:
            num = even_odd(num)
            print(num)
    elif problem_type == "physics":
        physics_solver()
    elif problem_type == "math":
        math_solver()
    else:
        print("Invalid problem type")

    problem_type = None  

