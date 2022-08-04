# CSP-StateMachine-Issue

Depedencies:
FishNet package
Note:
I used a 3D project with LTS 2021.3.7f1

How to Install
1. Click Code --> Download Zip
2. Extract ZIP
3. Create new Unity project, chosoe 3D
4. Click and drag the folder into Unity
5. Install Fishnet (I used the latest version 2.3.9)
6. Can create a build for server and use editor for client (more likely to see the issue this way I found) or use parrelsync (server and host looks fine, it's the client that jitters)

Issue: Whenever I change states, there's a bit of jitter. You can see it when jumping or if you bring the player close to the camera and rapidly press the "D" key (it switches from idle to walking), you can see the jitter there too. 

The jump jitter may only be visible at high frame rates, but it's definitely an issue, because it never happens when you don't change states.

To show the jump working smoothly without jitter, do these two things:

(1) In the PlayerMovementBaseState in the Move() method, Uncomment out     

        //if (md.IsJumpInputPressed && playerMovementStateMachine.ReusableData.Grounded)
        //{
        //    playerMovementStateMachine.ReusableData.VerticalVelocity = 4f;
        //}
        
 (2) Comment out Jump(); in the Move() method in the GroundedState
