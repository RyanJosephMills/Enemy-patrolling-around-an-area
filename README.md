# Enemy-patrolling-around-an-area

So, the first thing you must do to create an enemy patrol is create the two boundaries where the enemy can walk. To do this, you must create an empty object and call it patrol point 1, then click on the cube just above the transform section; these are called Gizmos. Once there, choose a gizmo that you like, and what this will do is make the patrol points easy to see and easy to place around the map. After that, you can duplicate them and put them wherever you want the enemy character to walk from and to.

![image](https://github.com/RyanJosephMills/Enemy-patrolling-around-an-area/assets/146854317/fac56655-de00-4092-981b-5e1c10145bdb)


Now that you have done that, you will need to start scripting to get the enemy to move around, so you will need to make a script called EnemyMovement and then open it up.

![image](https://github.com/RyanJosephMills/Enemy-patrolling-around-an-area/assets/146854317/f3f42157-a115-4e8b-b978-4b505d9caf2f)


Once you are inside the script, you will need to create some variables. The first one is a public Transform, and this will help us figure out which direction the enemy is heading in. Then you need to put [] patrolPoints as the name, and now you can go back inside of Unity and attach this script to the enemy, and now you can see inside of the inspector something called Patrol points. You will notice that these points are empty, so you must put in the patrol points we made earlier.

Now that you have made that, you must make the character move. You must return to the script and create a new variable, a public float moveSpeed, which will help you control the enemy's speed. Another variable you will need to make is a public int called patrolDestination, which will monitor which patrol point is currently the destination the enemy is heading in.

![image](https://github.com/RyanJosephMills/Enemy-patrolling-around-an-area/assets/146854317/f84dd021-4d1b-48e9-99e4-952c14ed78c7)


Now that you have all that, we can then go and delete the start function as we will not need it for this, and now we can go to the update section and create an if statement inside the brackets; you will need to put patrolDestination == 1 then in the curly brackets you will need to put transform.postion = Vector2.MoveTowards(transform.position, patrolPoints[1].position, moveSpeed * Time.deltaTime); this code will essentially move the character from wherever he spawns to patrol point 1. However, he will sit there once he gets to that point, as we haven’t told him what to do next. To do this, you must create an if statement and, inside the brackets, put a Vector2.Distance(transform.postion, patrolPoints[1].postion) < .2f) Then inside of the curly brackets you will need to put patrolDestination = 2; and essentially what this code is saying is that when the enemy character gets within the distance of .2 it will then turn around and start heading to the other patrol point, now what you can do is copy this whole bit of code and paste it underneath it and what you will need to do is change all the 1 to 2 and all the 2 to 1 and what this will do is it will do the same thing as the other code however it is from the other patrol point. The last thing you will need to do is make sure, inside Unity, that you add a movement speed; otherwise, the character will not move at all. Now that you have done this, you should have a fully working enemy movement system.

![image](https://github.com/RyanJosephMills/Enemy-patrolling-around-an-area/assets/146854317/415e26db-40e6-4985-8715-30b586fa9e83)

https://github.com/RyanJosephMills/Enemy-patrolling-around-an-area/assets/146854317/f13913f9-e1ba-42a7-94da-559aeedf6f33

