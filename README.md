# Udacity-projects
# Parallel parking program

car_parameters = {"throttle": 0, "steer": 0, "brake": 0}

def control(pos_x, pos_y, time, velocity):
    """ Controls the simulated car"""
    global car_parameters
    
    if(pos_y> 36):
        car_parameters["throttle"] = -1.0
        car_parameters["steer"] = 25
        car_parameters["brake"] = 0
    elif(pos_y < 36 and pos_y > 33):
        car_parameters["throttle"] = -1.0
        car_parameters["steer"] = -25
        car_parameters["brake"] = 0
    elif(pos_x < 128.5):
        car_parameters["throttle"] = 0
        car_parameters["steer"] = 0
        car_parameters["brake"] = 1
    else:
        car_parameters["throttle"] = 0
        car_parameters["steer"] = 0
        car_parameters["brake"] = 1

    return car_parameters
    
import src.simulate as sim
sim.run(control)
