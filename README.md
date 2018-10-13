# Mini-projet-1
def study (student):
    """ [student name] starts studying, impacts student's fatigue and education

    parameters
    ----------

    student : student name (str)
    fatigue: student fatigue (float)
    education: student education (float)
    
    Notes
    -----
    Needs fct [get_student_wellbeing(student)]
    Needs fct [get_student_education(student)]
    Needs fct [set_student_education(student, education)]
    
    """

    if get_student_wellbeing(student) >=7:
        
        set_student_education(student, get_student_education(student)+1)
        
    elif get_student_wellbeing(student) <=3:
        print('%s can\'t make progress' %student)
    else:
        from random import randint
        if randint(0,1) ==1:
            print('%s can\'t make any progress' %student)
        else:
            set_student_education(student,get_student_education(student)+0.5)
            
def sport (student,hour):
    """ [student name] starts doing sport for [hour] hours, 
    will feel better but have more fatigue 
    
    Parameters
    ----------
    
    student: student name (str)
    hours: number of hours doing sport (float)
    
    Notes
    -----
    Needs fct [get_student_wellbeing(student)]
    Needs fct [set_student_wellbeing]
    Needs fct [get_student_fatigue(student)]
    Needs fct [set_student_fatigue]
    
    """
    set_student_wellbeing(student,(get_student_wellbeing(student)+2*hour**2))
    set_student_fatigue(student,get_student_fatigue(student)+4*hour)
    
    
def talk (student,target_student):
    """[student] starts a conversation with [target_student], 
    makes the wellbeing of the saddest one go +1, but +2 fatigue for both
    
    Parameters
    ----------
    
    student: student name who talks (str)
    target_student: the student name who is talked to (str)
    """
    
    if get_student_wellbeing(student) > get_student_wellbeing(target_student):
        set_student_wellbeing(target_student, get_student_wellbeing(target_student)+1)
    
    elif get_student_wellbeing(student) < get_student_wellbeing(target_student):
        set_student_wellbeing(student, get_student_wellbeing(student)+1)
    
    else:
        set_student_wellbeing(student, get_student_wellbeing(student)+0.5)
        set_student_wellbeing(target_student, get_student_wellbeing(target_student)+0.5)
        
    set_student_fatigue(student, get_student_fatigue(student)+2)
    set_student_fatigue(target_student, get_student_fatigue(target_student)+2)
