# RAIL Model
## A User-Centric Performance Model. Based on the Web App Life Cycle.
- Response, Animation, Idle, Load

# Summary
- Focus on the User; The End Goal is to Make Users Happy, Not Just Perform Well on any Device
- Respond to Users immediately; User Input Should Be Acknowledge in 100ms.
- When Animating/Scrolling a Frame Should Be Produced in Under 10ms.
- Maximize Main Thread Idle Time.
- Keep Users Engaged, Deliver Interactice Content in Under 1000ms.

# Focus on the User
- The User should be the Focal Point of your Performance Effort. The Majority of Time Users Spend on your Site isn't Waiting for it to Load, but Waiting for it to Respond.

# How Users Perceive Performance Delay
## 0-16ms
- People can Easily Track Motion. Smooth is Perceived to be About 60 FPS. 16ms/Frame, including the Time it takes for a Browser to Paint a New Frame. You Have Approx 10ms to produce a Frame.

## 0-100ms
- Respond to a User Action within this Time Window and Users Feel like the Result is Immediate, any Longer and the Connection Between the Action and Reaction is Broken.

## 100-300ms
- Users Experience a Slight and Noticeable Delay.

## 300-1000ms
- Within this Window, Things can Feel a Part of the Natural and Continous Progression of Certain Tasks such as, Loading Pages or Changing Views.

## 1,000+ms
- Beyond 1 Second, Users Lose Focus on the Task they are Performing.

## 10,000ms
- User is Frustrated and Likely to Abandon the Task; May or May Not Return to the Web Application.


# Response: Respond in Under 100ms
- You have 100ms to Respond to a User before Lag is Noticed. Apply this to Most Inputs(Clicking Buttons, Form Controls, Starting Animations. Not Touch Drags or Scrolling). If you Don't Respond in Time, Users will Notice the Break between Action and Reaction.
- Sometimes Immediate Response to User Action is not Always Right. You Can Also Use This Window to do Other "Heavy" Work. Do not Block the User, if Possible do this in the Background.
- Always Provide Feedback for Responses Longer than 500ms.

# Animation: Produce a Frame in 10ms
- Users Notice When the Animation Frame Rate Varies. Your Goal is to Produce 60FPS.
- Every Frame goes Through These Steps -
Javascript -> Style -> Style -> Layout -> Paint -> Composite
- When Possible Use the 100ms Response to Pre-Calculate Expensive Work.
- Try to do Nothing Where Possible and as Little as Possible When You Cannot.

# Idle: Maximizing Idle Time
- Use Idle Time to Complete Deferred Work.
- Deferred Work Should be Chunked in 50ms Blocks.
- User Interaction is Highest Priority, and Should Take Over if Interaction Starts
- Using 50ms Blocks Allows Task to Finish While Still Providing Instant Response

# Load: Deliver Content in Under 1000ms
- Site Load Should Occur in Under 1 Second. Anything More and User Attention Wanders.
- Focus on Optimizing the Critical Rendering Path.
- You don't have to Load Everything Under 1 Second.
- Use Progressive Rendering and do Background Work.
- Defer Non-Essential Loads to Idle Periods

# RAIL Metrics
- Response, Input Latency from Tap to Paint Should Be < 100ms. Click/Tap a Button
- Animation, Each Frame's Work from JS to Paint Should Be < 16ms.
User Scrolls the Page.
- Idle, Main Thread in JS Work. Chunks of 50ms.
User is Not Interaction with the Page, but Enough Main Thread is Available to Handle Next User Input.
- Load, Page Ready to Use in Under 1 Second. User Should be Able to See Critical Path Content.
