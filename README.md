using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Numberwizzard : MonoBehaviour
{
	public bool gameover;
	public int Minimum; // Lowest number the player can choose
	public int Maximum; // Highest number the player can choose
	public int step; //step is a way to know what stage of the game it is in
	public int guess; // Chooses a number based on the players actions
	public string MyString ="Hello World";
    // Start is called before the first frame update
    void Start()
    {
		gameover = false;
		print("Welcome to Number Wizard");
		print("Pick a number between 1-10");
		print("I will try to guess the number you're thinking of");
		print("If the number I choose is lower than the one you're thinking of, press the up arrow");
		print("If the number I choose is higher than the one you're thinking of, press the down arrow");
		print("If I choose the correct number, press the ENTER button");
		
		guess = (Maximum + Minimum) / 2; //Computers 1st guess
		step = 0;
    }	
	

    //Update is called once per frame
    void Update()
    {
        //while (gameover == false) { 
           //print (MyString);	
		   
	//make sure to have == to be absolute

		//}
		if(step == 1)
		{
			print("Is your number " + guess + "?");
			if(Input.GetKeyDown(KeyCode.Return) && step == 0)
				
				{
					
					step += 1;
					
				}
				else
				{
					step -= 1;
					
				}
			string response = Console.ReadLine();
			step += (response == "y")? 1: -1; // ternary statement
		}
	}
}
