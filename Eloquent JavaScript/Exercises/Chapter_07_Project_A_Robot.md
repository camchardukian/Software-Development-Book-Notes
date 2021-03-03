# Chapter 7 -- Project: A Robot

Note from Cam: For brevity's sake I'm simply going to put my solutions to the following exercises here. For explanations of what each exercise entails, please refer to the [free online version of this chapter here](https://eloquentjavascript.net/07_robot.html).

If you are having trouble with this chapter, I also recommend watching [this video](https://www.youtube.com/watch?v=PK2rB9VGWSA). I felt the professor in that video introduced the ideas in this chapter in a much clearer manner than the author of this book.

Here are my solutions for this chapter's exercises.

---

## Measuring a robot

**My solution:**

**Brainstorming...**

```
function compareRobots(robot1, memory1, robot2, memory2) {
  const villageState = VillageState.random();
  console.log(villageState)
  console.log(typeof villageState)
  // currently getting errors because villageState is an object
  // and routeRobot uses the length property which is looking for an array.
  runRobot(villageState, robot1(), [])
}

compareRobots(routeRobot, [], goalOrientedRobot, []);
```

**Refining...**

```
function compareRobots(robot1, memory1, robot2, memory2) {
  const villageState = VillageState.random();
  const robotOneNumberOfTurns = sendRobotOnDeliveryRoute(villageState, robot1, memory1)
  const robotTwoNumberOfTurns = sendRobotOnDeliveryRoute(villageState, robot2, memory2)
  console.log('robotOneNumberOfTurns', robotOneNumberOfTurns)
  console.log('robotTwoNumberOfTurns', robotTwoNumberOfTurns)
}

const sendRobotOnDeliveryRoute = (state, robot, memory) => {
 for (let turn = 0; turn < 100; turn++) {
   let action = robot(state, memory);
    state = state.move(action.direction);
    memory = action.memory;
   if (state.parcels.length == 0) {
    return turn
   }
 }
}

function runRobot(state, robot, memory) {
  for (let turn = 0;; turn++) {
    if (state.parcels.length == 0) {
      console.log(`Done in ${turn} turns`);
      break;
    }
    let action = robot(state, memory);
    state = state.move(action.direction);
    memory = action.memory;
    console.log(`Moved to ${action.direction}`);
  }
}
compareRobots(routeRobot, [], goalOrientedRobot, []);
```

**Final solution**

```
function compareRobots(robot1, memory1, robot2, memory2) {
  const villageState = VillageState.random(100);
  const robotOneNumberOfTurns = sendRobotOnDeliveryRoute(villageState, robot1, memory1);
  const robotTwoNumberOfTurns = sendRobotOnDeliveryRoute(villageState, robot2, memory2);
  const result = {robot1: robotOneNumberOfTurns / 100, robot2: robotTwoNumberOfTurns / 100};
  return result;
}

const sendRobotOnDeliveryRoute = (state, robot, memory) => {
 for (let turn = 0; turn < 100; turn++) {
   let action = robot(state, memory);
    state = state.move(action.direction);
    memory = action.memory;
   if (state.parcels.length == 0) {
    return turn;
   }
 }
}

compareRobots(routeRobot, [], goalOrientedRobot, []);
```

**Thoughts**:
When I first finished the chapter and tried tackling this exercise I had absolutely no idea what I needed to do.

Once I read over the chapter again, and watched [this video](https://www.youtube.com/watch?v=PK2rB9VGWSA), however, it took me only a few iterations before I was able to solve this problem.

---

## Robot efficiency

**My solution:**

Err... ummm... Yeah, I got nothing. I tried for 45 minutes or so, but didn't come away with much of anything concrete to show for my efforts.

**Thoughts:**
I logically reasoned that I could improve the _goalOrientedRobot_ by taking into account all of the parcels it needed to be delivered and finding the shortest route that encompassed each of the necessary points rather than calculating individual optimal routes.

I then went through the code base and asked myself _what does this function do?_, _what does this variable do?_ until I had clearly defined and written down what a large portion of the code base did.

Even despite this planning, however, I still couldn't think of a way to actually implement everything. :(

---

## Persistent group

**My solution:**

Coming soon...
