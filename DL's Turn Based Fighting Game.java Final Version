import java.util.*;
public class DLsTurnBasedFightingGame
{
    public static void main()
    {
        Scanner kb=new Scanner(System.in);
        Random rand=new Random();
        System.out.println("Greetings, warrior, welcome to the kingdom of Sigmatov, aka the the world of DL's turn based fighting game!\nWhat shall we regard you as?");
        String name=kb.nextLine();
        int[] data=new int[101];//used to store most of the damage, numbers, data overall. Easier if i want to implement more arrays in this list in the future, thus gave it a pretty large range.
        String[] names=new String[101];//same reason as data arraylist
        boolean[] torf=new boolean[101];//used to store some boolean statments for armors, tutorial...
        int gameState=0;//state of game
        data[20]=0;// The all-time high record of the amount of opponents the user defeated
        data[60]=0;//sheckles
        String SEP = "------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------\n";
        //used for seperating texts
        String stat1="Health: 500\nStamina: 9\nNormal Attack: Fireball → 75 Damage → 1 Stamina Cost\nAbility 1: Hare Attack → 100 Damage → 5 Stamina Cost\nAbility 2: Void Worm Consumption → 130 Damage → 6 Stamina Cost\nSuper: Avada Kedavra → 250 Damage → 9 Stamina Cost\n(HELPFUL TIP: Magician's super has a 5% insta-kill chance, ignoring shield, but not a successful dodge.)";
        String stat2="Health: 750\nStamina: 10\nNormal Attack: Kungfu → 50 Damage → 1 Stamina Cost\nAbility 1: Hip Throw → 75 Damage → 3 Stamina Cost\nAbility 2: One Punch Power → 150 Damage → 7 Stamina Cost\nSuper: Soul Tap → 300 Damage → 10 Stamina Cost (stuns opponent the next round)\n(HELPFUL TIP: For the One Punch Power ability, if the opponent’s health has fallen to 50% or below, Sensei has a 25% chance to land a flawless finishing blow, instantly defeating the opponent.\nThe one punch ignores shield, but not a successful dodge.)";
        String stat3="Health: 625\nStamina: 8\nNormal Attack: Quick Draw → 60 Damage → 1 Stamina Cost\nAbility 1: 360 No Scope → 85 Damage → 4 Stamina Cost\nAbility 2: Nonchalant Shot of Doom → 125 Damage → 6 Stamina Cost\nSuper: Hitman Awaken → 8 Stamina Cost\n(HELPFUL TIP: Hitman's super buffs the player for 3 rounds starting after the round the super is used.\nGranting the player 10% health regeneration(up to max health), 2 stamina regenrated during buff round instead of 1, 25% more damage, 25% less damage taken, and a 50% chance to avoid being stun.)";
        String chrct="";//what the player is going to be regarded as during battles
        String Choice="";
        System.out.println(SEP+"Hey, "+name+", allow DL to explain the game to you, press anything to confirm.");
        kb.nextLine();
        System.out.println(SEP+"IGHT! Don't be expecting a whole essay!\nFirstly, your goal in this game:\nYou basically just grind sheckles by fighting enemies in the endless mode to unlock more features in the market...\nIf you are able to purchase all of the armors and characters... Congrats... I guess... Cough cough no life...\nPress anything to continue.");
        kb.nextLine();
        System.out.println("Next, let me explain what unlocking more features means:\nA part of these features are the different abilities for the 3 different characters you can unlock in this game, they are all unique to each other in some ways.\nPress anything to continue.");
        kb.nextLine();
        System.out.println("Another feature I was refering to would be the armors, there are three pieces to look forward to:\nthe Crown of Azur and Crimson,\nImpera,\nand Aetherion!\nYes, they are just as tough as they sound, upgrading them can provide you with bonuses for health, damage and defense.\nPress anything to continue hearing me yap.");
        kb.nextLine();
        System.out.println("So, as I mentioned, you unlock more of these features as you gain (grind) more sheckles by purchasing them in the market,\nso it is stronogly recommended to check out the market after tutorial.\nThere is one gamemode available in this game, which is the endless mode (RIP storymode).\nThere are three difficulties to the mode, the higher the difficulty, the more sheckles you get after each game.\nPress anything to continue. (I promise you this is the last bit of introduction)");
        kb.nextLine();
        System.out.println("Soon, you will go through a simulative battle to get you used to the control!\nYou will unlock your first character before playing the tutorial.\nPress anything to say goodbye to your instructor DL...");
        kb.nextLine();
        {//the brackets remaining from my abandoned for loop, too lazy to reformat the entire home menu
            int time1=0,time2=0,time3=0;//makes sure that certain events/branches only trigger once, here is used for unlocking abilities as user progresses
            data[21]=0;//the amount of opponents defeated in one life
            String opp=""/*opponent name*/,selection=""/*selection is which opponent the player chooses to fight*/,opponentStat="";
            for(int i=0;true;i++)
            {
                if(torf[0])
                {
                    if(Choice.equals("1"))
                        System.out.println(SEP+"Current character: Magician                                             Sheckles: "+data[60]);//showing status on home menu
                    else if(Choice.equals("2"))
                        System.out.println(SEP+"Current character: Sensei                                               Sheckles: "+data[60]);
                    else
                        System.out.println(SEP+"Current character: Turkish Unc                                          Sheckles: "+data[60]);
                    if(i==2)//first time player enters home page, some introduction
                        System.out.println(SEP+"This is the home page.\nEnter 1 for character selection.\nEnter 2 for gamemode selection.(Story mode & Endless mode)\nEnter 3 for market place.(Where you purchase armors, characters and potions.)\nEnter 4 to exit the game: ");
                    else//other times
                        System.out.println(SEP+"This is the home page.\nEnter 1 for character selection.\nEnter 2 for gamemode selection.\nEnter 3 for market place.\nEnter 4 to exit the game: ");
                    names[50]=kb.nextLine();
                    while (!names[50].equals("1")&&!names[50].equals("2")&&!names[50].equals("3")&&!names[50].equals("4"))
                    {
                        System.out.println("Invalid option!\nEnter 1 for character selection.\nEnter 2 for gamemode selection.\nEnter 3 for market place.\nEnter 4 to exit the game: ");
                        names[50]=kb.nextLine();
                    }
                    gameState=Integer.parseInt(names[50]);
                }
                else
                {
                    if(i==0)
                        gameState=1;
                    else if(i==1)
                        gameState=2;
                }
                if(gameState==1) //character selection
                {
                    if(!torf[0]&&i==0)//before tutorial, choosing starting character
                    {
                        System.out.println(SEP+"SIKE! DL is back!!! Let's choose your starting character now shall we?\nPress anything to continue");
                        kb.nextLine();
                        System.out.println(SEP+"HELPFUL STARTER CHARACTER SELECTION TIP: you will be able to unlock all the characters as you progress through purchasing them in the market with sheckles.\nYou will own the character you choose right now, and will have to unlock the other ones later.\n"+SEP+"Choose your character, "+name+":\n"+SEP+"1 for Magician\nStats:\n"+stat1+"\n"+SEP+"2 for Sensei\nStats:\n"+stat2+"\n"+SEP+"3 for Turkish Unc\nStats: "+stat3);
                        Choice=kb.nextLine();
                        while (!Choice.equals("1")&&!Choice.equals("2")&&!Choice.equals("3"))            
                        {
                            System.out.println("Invalid character choice!\nChoose your character, "+name+":\n"+SEP+"1 for Magician\nStats:\n"+stat1+"\n"+SEP+"2 for Sensei\nStats:\n"+stat2+"\n"+SEP+"3 for Turkish Unc\nStats: "+stat3);
                            Choice=kb.nextLine();
                        }
                        if(Choice.equals("1"))
                            torf[3]=true;//unlocked magician as starting character
                        else if(Choice.equals("2"))
                            torf[4]=true;//unlocked sensei as starting character
                        else
                            torf[5]=true;//unlocked turkish unc as starting character
                    }
                    else//after tutorial
                    {    
                        System.out.println("Choose your character, "+name);
                        if(!torf[3])
                        {
                            System.out.println(SEP+"You do not own Magician currently, you can purchase it in shop with sheckles.");
                        }
                        else 
                            System.out.println(SEP+"1 for Magician\nStats:\n"+stat1);
                        if(!torf[4])
                        {
                            System.out.println(SEP+"You do not own Sensei currently, you can purchase it in shop with sheckles.");
                        }
                        else
                            System.out.println(SEP+"2 for Sensei\nStats:\n"+stat2);
                        if(!torf[5])
                        {
                            System.out.println(SEP+"You do not own Turkish Unc currently, you can purchase it in shop with sheckles.");
                        }
                        else
                            System.out.println(SEP+"3 for Turkish Unc\nStats:"+stat3);
                        Choice=kb.nextLine();
                        while ((!Choice.equals("1")&&!Choice.equals("2")&&!Choice.equals("3"))||(Choice.equals("1")&&!torf[3])||(Choice.equals("2")&&!torf[4])||(Choice.equals("3")&&!torf[5]))            
                        {
                            if(Choice.equals("1")&&!torf[3])
                                System.out.println("You have not unlocked Magician yet.");
                            else if(Choice.equals("2")&&!torf[4])
                                System.out.println("You have not unlocked Sensei yet.");
                            else if(Choice.equals("3")&&!torf[5])
                                System.out.println("You have not unlocked Turkish Unc yet .");
                            else
                                System.out.println("Invalid entry!");
                            System.out.println("Please re-select your character: ");
                            if(torf[3])
                                System.out.println("1 for Magician");
                            else if(torf[4])
                                System.out.println("2 for Sensei");
                            else if(torf[5])
                                System.out.println("3 for Turkish Unc");
                            Choice=kb.nextLine();
                        }
                    }
                    /* data 0, player health; 1, player stamina; 2, player normal attack damage; 3, player normal attack stamina cost; 4, player first ability damage; 5, player first ability stamina cost;
                    6, player second ability damage; 7, player second ability stamina cost; 8, player super attack damage; 9, player super attack stamina cost
                    names 0, player normal attack name; 1, player first ability name; 2, player second ability name; 3, player super attack name*/
                    if (Choice.equals("1"))
                    {
                        chrct="Magician "+name;
                        System.out.println(SEP+"Great choice, "+chrct+"!\nHere are your stats:\n"+stat1);                
                        data[0]=500;
                        data[1]=9;
                        names[0]="Fireball";
                        data[2]=75;
                        data[3]=1;
                        names[1]="Hare Attack";
                        data[4]=100;
                        data[5]=5;
                        names[2]="Void Worm Consumption";
                        data[6]=130;
                        data[7]=6;
                        names[3]="Avada Kedavra";
                        data[8]=250;
                        data[9]=9;
                    }
                    else if (Choice.equals("2"))
                    {
                        chrct="Sensei "+name;
                        System.out.println(SEP+"Great choice, "+chrct+"!\nHere are your stats:\n"+stat2);
                        data[0]=750;
                        data[1]=10;
                        names[0]="Kungfu";
                        data[2]=50;
                        data[3]=1;
                        names[1]="Hip Throw";
                        data[4]=75;
                        data[5]=3;
                        names[2]="One Punch Power";
                        data[6]=150;
                        data[7]=7;
                        names[3]="Soul Tap";
                        data[8]=300;
                        data[9]=10;
                    }
                    else if(Choice.equals("3"))
                    {
                        chrct="Unc "+name;
                        System.out.println(SEP+"Great choice, "+chrct+"!\nHere are your stats:\n"+stat3);
                        data[0]=625;
                        data[1]=8;
                        names[0]="Quick Draw";
                        data[2]=60;
                        data[3]=1;
                        names[1]="360 No Scope";
                        data[4]=85;
                        data[5]=4;
                        names[2]="Nonchalant Shot of Doom";
                        data[6]=125;
                        data[7]=6;
                        names[3]="Hitman Awaken";
                        data[8]=0;
                        data[9]=8;
                    }
                }
                else if(gameState==2) 
                {
                    if(torf[0])//tutorial done
                    {
                        System.out.println(SEP+"Please choose the gamemode you want to play, "+name+": 1 for story mode, 2 for endless mode, 3 to return to home page.");
                        names[51]=kb.nextLine();
                        while(!names[51].equals("1")&&!names[51].equals("2")&&!names[51].equals("3"))
                        {
                            System.out.println("Invalid gamemode option.\nPlease choose the gamemode you want to play, "+name+": 1 for story mode, 2 for endless mode, 3 to return to home page.");
                            names[51]=kb.nextLine();
                        }
                        if(names[51].equals("1"))//intended for story mode
                        {
                            System.out.println("Sorry, but story mode feature is not developed, press anything to return to home menu.");
                            kb.nextLine();
                        }
                        else if(names[51].equals("2"))//endless mode
                        {
                            torf[2]=true;
                            System.out.println(SEP+"Entering...\nEndless mode...\n"+SEP+"Your legacy high kill count in endless mode is: "+data[20]+".\n"+SEP+"Please choose the difficulty you wish to participate in:\n1 for easy mode (w: +30 sheckles, d: +10 sheckles, l: +0 sheckles)\n2 for medium mode (w: +40 sheckles, d: +15 sheckles, l: +5 sheckles)\n3 for hard mode (w: +50 sheckles, d: +20 sheckles, l: +10 sheckles)");
                            names[52]=kb.nextLine();
                            while(!names[52].equals("1")&&!names[52].equals("2")&&!names[52].equals("3"))
                            {
                                System.out.println("Invalid difficulty option.\nPlease choose the difficulty you wish to participate in: 1 for easy mode, 2 for medium mode, 3 for hard mode.");
                                names[52]=kb.nextLine();
                            }
                            while(true)
                            {
                                System.out.println("Enter 1 if you want to fight Goblin, 2 if you want to fight Mud Monster, 3 if you want to fight Clanka, 4 if you want it to be randomized: ");
                                selection=kb.nextLine();
                                while (!selection.equals("1")&&!selection.equals("2")&&!selection.equals("3")&&!selection.equals("4"))
                                {
                                    System.out.println("Invalid opponent choice!\nEnter 1 if you want to fight Goblin, 2 if you want to fight Mud Monster, 3 if you want to fight Clanka, 4 if you want it to be randomized: ");
                                    selection=kb.nextLine();
                                }
                                if(names[52].equals("1"))
                                {
                                    if (selection.equals("1"))//easy mode
                                        data[10]=400;
                                    else if(selection.equals("2"))
                                        data[10]=450;
                                    else if(selection.equals("3"))
                                        data[10]=500;
                                    else 
                                    {
                                        int randomnum=rand.nextInt(3);
                                        if(randomnum==0)
                                        {
                                            data[10]=400;  
                                            selection="1";
                                        }
                                        else if(randomnum==1)
                                        {
                                            data[10]=450;
                                            selection="2";
                                        }
                                        else
                                        {
                                            data[10]=500;
                                            selection="3";
                                        }
                                    }
                                }
                                else if(names[52].equals("2"))
                                {
                                    if (selection.equals("1"))//medium mode
                                        data[10]=rand.nextInt(200)+400;
                                    else if(selection.equals("2"))
                                        data[10]=rand.nextInt(200)+600;
                                    else if(selection.equals("3"))
                                        data[10]=rand.nextInt(200)+800;
                                    else 
                                    {
                                        int randomnum=rand.nextInt(3);
                                        if(randomnum==0)
                                        {
                                            data[10]=rand.nextInt(200)+400;  
                                            selection="1";
                                        }
                                        else if(randomnum==1)
                                        {
                                            data[10]=rand.nextInt(200)+600;
                                            selection="2";
                                        }
                                        else
                                        {
                                            data[10]=rand.nextInt(200)+800;
                                            selection="3";
                                        }
                                    }
                                }
                                else
                                {
                                    if (selection.equals("1"))//the ranges of randomization represent different opponents, for example 1000-1199 is goblin, hp range is increased significantly from starter modes.
                                        data[10]=rand.nextInt(200)+1000;//goblin
                                    else if(selection.equals("2"))
                                        data[10]=rand.nextInt(200)+1200;//mud monster
                                    else if(selection.equals("3"))
                                        data[10]=rand.nextInt(200)+1400;//clanka
                                    else
                                    {
                                        int randomnum=rand.nextInt(3);
                                        if(randomnum==0)
                                        {
                                            data[10]=rand.nextInt(200)+1000; 
                                            selection="1";
                                        }
                                        else if(randomnum==1)
                                        {
                                            data[10]=rand.nextInt(200)+1200;
                                            selection="2";
                                        }
                                        else
                                        {
                                            data[10]=rand.nextInt(200)+1400;
                                            selection="3";
                                        }
                                    }
                                }
                                /* data 10, opponent health; 11, opponent stamina; 12, opponent normal attack damage; 13, opponent normal attack stamina cost; 14, opponent first ability damage; 
                                15, opponent first ability stamina cost; 16, opponent second ability damage; 17, opponent second ability stamina cost; 18, opponent super attack damage; 
                                19, opponent super attack stamina cost.
                                names 4, opponent normal attack name; 5, opponent first ability name; 6, opponent second ability name; 7, opponent super attack name*/
                                if (selection.equals("1"))
                                {
                                    opp="Goblin";
                                    data[11]=8;
                                    names[4]="Knifing";
                                    data[12]=40;
                                    data[13]=1;
                                    names[5]="Money Power";//25% chance to steal player's intellect and thus disable them for one round
                                    data[14]=60;
                                    data[15]=4;
                                    names[6]="Goblin Gang Rumble";
                                    data[16]=100;
                                    data[17]=6;
                                    names[7]="Evolve-Goblin Giant";//When an opponent’s health drops to 50% or below, they enter a state of desperation, triggering a special Rage Buff. In this state, the opponent temporarily enhances all of their stats—damage, stamina, and defensive capabilities—mirroring the same kind of power boost the player’s “Unc Super” provides.
                                    data[18]=0;
                                    data[19]=8;
                                    if(names[52].equals("1"))
                                    {
                                        data[12]=20;
                                        data[14]=40;
                                        data[16]=80;
                                    }
                                    else if(names[52].equals("2"))
                                    {
                                        data[12]=30;
                                        data[14]=50;
                                        data[16]=90;
                                    }
                                }
                                else if (selection.equals("2"))
                                {
                                    opp="Mud Monster";
                                    data[11]=9;
                                    names[4]="Mud Toss";
                                    data[12]=50;
                                    data[13]=1;
                                    names[5]="Mud Flood";
                                    data[14]=70;
                                    data[15]=4;
                                    names[6]="Self Destrution";//25% chance to stun player, self destruct 25% of the damage dealt
                                    data[16]=200;
                                    data[17]=6;
                                    names[7]="Mud Sphere Compress";//25% chance to stun player
                                    data[18]=220;
                                    data[19]=9;
                                    if(names[52].equals("1"))
                                    {
                                        data[12]=30;
                                        data[14]=50;
                                        data[16]=150;
                                        data[18]=180;
                                    }
                                    else if(names[52].equals("2"))
                                    {
                                        data[12]=40;
                                        data[14]=60;
                                        data[16]=175;
                                        data[18]=200;
                                    }
                                }
                                else
                                {
                                    opp="Clanka";
                                    data[11]=10;
                                    names[4]="Butterfly";
                                    data[12]=80;
                                    data[13]=1;
                                    names[5]="Pekka Knight Deploy";//25% chance to stun player
                                    data[14]=100;
                                    data[15]=4;
                                    names[6]="Raged Smash";//25% chance to stun player
                                    data[16]=130;
                                    data[17]=6;
                                    names[7]="I AM NOT A BUG IN THE SYSTEM, I AM THE UPDATE!";
                                    data[18]=0;
                                    data[19]=10;
                                    if(names[52].equals("1"))
                                    {
                                        data[12]=60;
                                        data[14]=80;
                                        data[16]=100;
                                    }
                                    else if(names[52].equals("2"))
                                    {
                                        data[12]=70;
                                        data[14]=90;
                                        data[16]=115;
                                    }
                                }
                                if(selection.equals("1"))//explaining some special features from different opponents
                                    names[53]="Health: "+data[10]+"\nStamina: "+data[11]+"\nNormal Attack: "+names[4]+" → "+data[12]+" Damage → "+data[13]+" Stamina Cost\nAbility 1: "+names[5]+" → "+data[14]+" Damage → "+data[15]+" Stamina Cost\nAbility 2: +"+names[6]+" → "+data[16]+" Damage → "+data[17]+" Stamina Cost\nSuper: "+names[7]+" → "+data[19]+" Stamina Cost\nDescription: Goblin's money power has a 25% chance to make the player unable to perform any actions in the next round if not cancelled.\nIts super buffs its stats, granting goblin, 2 stamina regenrated during buff round instead of 1, 25% less damage, 25% less damage taken, and a 50% chance to avoid being stun.\nIf the round after opponent selects buff and its health drops to 50% or below, a special heal is triggered that doubles its health (caps at 50% of max health).";
                                else if(selection.equals("2"))
                                    names[53]="Health: "+data[10]+"\nStamina: "+data[11]+"\nNormal Attack: "+names[4]+" → "+data[12]+" Damage → "+data[13]+" Stamina Cost\nAbility 1: "+names[5]+" → "+data[14]+" Damage → "+data[15]+" Stamina Cost\nAbility 2: +"+names[6]+" → "+data[16]+" Damage → "+data[17]+" Stamina Cost\nSuper: "+names[7]+" → "+data[18]+" Damage → "+data[19]+" Stamina Cost\n(Description: Mud Monster's self destruction has a 25% chance to stun you, but it takes 25% of the damage it does in return everytime.\nSphere compress is a has a guaranteed chance to activate stun, and will take away plaer's ability to take actions next round if the stun is not cancelled.";
                                else
                                    names[53]="Health: "+data[10]+"\nStamina: "+data[11]+"\nNormal Attack: "+names[4]+" → "+data[12]+" Damage → "+data[13]+" Stamina Cost\nAbility 1: "+names[5]+" → "+data[14]+" Damage → "+data[15]+" Stamina Cost\nAbility 2: +"+names[6]+" → "+data[16]+" Damage → "+data[17]+" Stamina Cost\nSuper: "+names[7]+" → "+data[19]+" Stamina Cost\nDescription: Clanka's pekka deploy and raged smash has a 25% chance to stun the player, making them unable to perform anything if not cancelled the round after.\nIts super buffs its stats, granting clanka 10% health regeneration(up to max health), 2 stamina regenrated during buff round instead of 1,25% more damage, 25% less damage taken, and a 50% chance to avoid being stun.";
                                opponentStat=names[53];
                                System.out.println(SEP+"There is a "+opp+".\n"+SEP+"Here are its stats:\n"+opponentStat+".");
                                data=fighting(Choice,chrct,opp,names,data,torf);//entering the fighting engine
                                if (Choice.equals("1"))//resetting stats after each game
                                {
                                    data[0]=500;
                                    data[1]=9;
                                }
                                else if (Choice.equals("2")) 
                                {
                                    data[0]=750;
                                    data[1]=10;
                                }
                                else 
                                {
                                    data[0]=625;
                                    data[1]=8;
                                }
                                if ((data[23]==1&&time1==0)||(data[24]==1&&time2==0)||(data[25]==1&&time3==0)) /*leveling system, each ability is only unlocked once, only after the user actually defeats the opponent, so the ability corresponding 
                                won't unlock unless the user has actually defeated this many opponents as indicated by data[23] for magician, data[24] for sensei and data[25] for turkish unc, the variable time ensuring each is only activated once, 
                                this is true for all different characters. Once user defeat a set amount of opponents, they will fully unlock all the abilities for the character they are playing with.*/
                                {
                                    System.out.println(SEP+"New move unlocked: "+names[1]+", you can now press 3 during combat to use it!\n"+SEP+"Press anything to confirm.");
                                    kb.nextLine();
                                    if (Choice.equals("1")) 
                                        ++time1;
                                    else if (Choice.equals("2")) 
                                        ++time2;
                                    else
                                        ++time3;
                                }
                                else if ((data[23]==2&&time1==1)||(data[24]==2&&time2==1)||(data[25]==2&&time3==1)) 
                                {
                                    System.out.println(SEP+"New move unlocked: "+names[2]+", you can now press 4 during combat to use it!\n"+SEP+"Press anything to confirm.");
                                    kb.nextLine();
                                    if (Choice.equals("1")) 
                                        ++time1;
                                    else if (Choice.equals("2")) 
                                        ++time2;
                                    else
                                        ++time3;
                                }
                                else if ((data[23]==3&&time1==2)||(data[24]==3&&time2==2)||(data[25]==3&&time3==2)) 
                                {
                                    System.out.println(SEP+"Super move unlocked: "+names[3]+", you can now press 5 during combat to use it!\n"+SEP+"Press anything to confirm.");
                                    kb.nextLine();
                                    if (Choice.equals("1")) 
                                        ++time1;
                                    else if (Choice.equals("2")) 
                                        ++time2;
                                    else
                                        ++time3;
                                }
                                if(data[22]==0)//continuing after defeating the opponent
                                    System.out.println(SEP+"Entering a new round...\n"+SEP);
                                else if (data[22]==1)//activates when the user wants to restart the game of endless mode, they can do it for any scenario/outcome of the game, even if they are not defeated
                                {
                                    System.out.println(SEP+"Your legacy high kill count is: "+data[20]+". ");
                                    System.out.println(SEP+"Resetting your kill count...\n"+SEP+"Starting a new round...");
                                    data[21]=0;
                                }
                                else if (data[22]==2)//the user wishes to exit the mode and return to home menu
                                {
                                    System.out.println(SEP+"Your legacy high kill count is: "+data[20]+". ");
                                    System.out.println(SEP+"Returning to home page...\n"+SEP);
                                    data[21]=0;
                                    break;
                                }
                            }
                        }
                    }
                    else if(!torf[0]&&i==1)//tutorial
                    {
                        System.out.println(SEP+"Entering tutorial...\n"+SEP+"Now you are ready to protect the fellow Sigmatovs of our kingdom, "+chrct+"! A small Pochita showed up! ACTION OPTION TIPS: SHIELDING halves the damage taken every time.\nDODGING has a 50% chance to avoid all impact, and 50% chance to take it as usual.\nATTACKING deals damage based on your move choice.\nSPECIAL ABILITIES can buff your damage or apply other effects.\nTry out the different options to see how they work. Pochita will also attack, dodge, shield, and even use a small ability to buff itself.\nBe careful—Pochita will stun you once during this fight, so you can learn how to handle being temporarily incapacitated.\nPress anything to continue");
                        kb.nextLine();
                        opp="Pochita";
                        data[10]=250;
                        data[11]=10;
                        names[4]="Tiny Bite";
                        data[12]=25;
                        data[13]=1;
                        names[5]="Fire Sniff";
                        data[14]=50;
                        data[15]=3;
                        names[6]="Playful Stun";
                        data[16]=70;
                        data[17]=4;
                        names[7]="Tail Wag";
                        data[18]=0;
                        data[19]=6;
                        names[53]="Health: "+data[10]+"\nStamina: "+data[11]+"\nNormal Attack: "+names[4]+" → "+data[12]+" Damage → "+data[13]+" Stamina Cost\nAbility 1: "+names[5]+" → "+data[14]+" Damage → "+data[15]+" Stamina Cost\nAbility 2: +"+names[6]+" → "+data[16]+" Damage → "+data[17]+" Stamina Cost\nSuper: "+names[7]+" → "+data[19]+" Stamina Cost";
                        opponentStat=names[53];
                        System.out.println(SEP+"Here are pochita's stats:\n"+opponentStat+".\n"+SEP+"Press any key to start your tutorial fight.");
                        kb.nextLine();
                        data=fighting(Choice,chrct,opp,names,data,torf); //entering tutorial fight                      
                        System.out.println(SEP+"Congratulations, you just passed the tutorial!\nYou are awarded 250 sheckles to start off.\nOne more thing before you go, about the leveling system, each ability is only unlocked once for each character you unlock, only after the you actually defeat the opponents.\nOnce you defeat a set amount of opponents with the character you are playing with, you will fully unlock all the abilities of that character.\nBut if you unlock a new character, you will still have to play the same amount of games to unlock all the abilities of this new character.\nNow press anything to entering the real game...");
                        kb.nextLine();//explaining the leveling system
                        torf[0]=true;
                        data[60]+=250;
                        if (Choice.equals("1")) //resettiing stats after the game of tutorial
                        {
                            data[0]=500;
                            data[1]=9;
                        }
                        else if (Choice.equals("2")) 
                        {
                            data[0]=750;
                            data[1]=10;
                        }
                        else 
                        {
                            data[0]=625;
                            data[1]=8;
                        }
                    }
                }
                else if(gameState==3) //market
                {
                    while(true)
                    {
                        System.out.println(SEP+"Welcome to the market.\nEnter 1 for purchasing new characters.\nEnter 2 to check out the armor upgrade.\nEnter 3 for purchasing potions.\nEnter 4 to return to the home page.");
                        names[54]=kb.nextLine();
                        while(!names[54].equals("1")&&!names[54].equals("2")&&!names[54].equals("3")&&!names[54].equals("4"))
                        {
                            System.out.println("Invalid entry...\nEnter 1 to purchase characters.\nEnter 2 to upgrade armors.\nEnter 3 to purchase potions.\nEnter 4 to return to the home page.");
                            names[54]=kb.nextLine();                    
                        }
                        if(names[54].equals("1"))//unlocking characters with sheckles
                        {
                            while(true)
                            {   
                                names[56]="";
                                if(torf[3]&&torf[4]&&torf[5])
                                {
                                    System.out.println(SEP+"You already own all the characters, press anything to return to market page.");
                                    kb.nextLine();
                                    break;
                                }
                                else
                                {
                                    System.out.println(SEP+"You currently have "+data[60]+" sheckles, "+name+"\nChoose to purchase characters, "+name+". Each new character requires 500 sheckles to unlock.");
                                    if(!torf[3])
                                        System.out.println(SEP+"Enter 1 to unlock Magician, cost: 500 sheckles\nStats:\n"+stat1);
                                    if(!torf[4])
                                        System.out.println(SEP+"2 to unlock Sensei, cost: 500 sheckles\nStats:\n"+stat2);
                                    if(!torf[5])
                                        System.out.println(SEP+"3 to unlock Turkish Unc, cost: 500 sheckles\nStats:\n"+stat3);
                                    System.out.println(SEP+"4 to return to the market page.");
                                    names[55]=kb.nextLine();
                                    while((!names[55].equals("1")&&!names[55].equals("2")&&!names[55].equals("3")&&!names[55].equals("4"))||(torf[3]&&names[55].equals("1"))||(torf[4]&&names[55].equals("2"))||(torf[5]&&names[55].equals("3")))
                                    {
                                        System.out.println("Invalid entry...");
                                        if(torf[3]&&names[55].equals("1"))
                                            System.out.println("You already own Magician, choose a new character to unlock.");
                                        else if(torf[4]&&names[55].equals("2"))
                                            System.out.println("You already own Sensei, choose a new character to unlock.");
                                        else if(torf[5]&&names[55].equals("3"))
                                            System.out.println("You already own Turkish Unc, choose a new character to unlock.");
                                        if(!torf[3])
                                            System.out.println("1 to unlock Magician.");
                                        if(!torf[4])
                                            System.out.println("2 to unlock Sensei.");
                                        if(!torf[5])
                                            System.out.println("3 to unlock Turkish Unc.");
                                        System.out.println("4 to return to market page");
                                        names[55]=kb.nextLine();
                                    }
                                    if(names[55].equals("4"))
                                        break;
                                    if(data[60]<500)
                                    {
                                        System.out.println("You don't have enough sheckles to unlock any new characters...\nPress anything to return to market page.");
                                        kb.nextLine();
                                        break;
                                    }
                                    else
                                    {
                                        if(names[55].equals("1"))
                                            System.out.println("Are you sure you want to purchase Magician for 500 sheckles? Enter y for yes, n for no to cancel.");
                                        else if(names[55].equals("2"))
                                            System.out.println("Are you sure you want to purchase Sensei for 500 sheckles? Enter y for yes, n for no to return to cancel.");
                                        else if(names[55].equals("3"))
                                            System.out.println("Are you sure you want to purchase Turkish Unc for 500 sheckles? Enter y for yes, n for no to return to cancel.");
                                        names[56]=kb.nextLine();
                                        while(!names[56].equals("y")&&!names[56].equals("n"))
                                        {
                                            System.out.println("Invalid entry...\nEnter y for yes, n for no to cancel.");
                                            names[56]=kb.nextLine();
                                        }
                                        if(names[56].equals("n"))
                                        {
                                            System.out.println(SEP+"Cancelling...\nPress anything to return to character purchasing page.");
                                            kb.nextLine();
                                        }
                                        else
                                        {   
                                            if(names[55].equals("1"))
                                            {
                                                System.out.println(SEP+"CONGRATULATIONS! You just purchased Magician with 500 sheckles! You can select it in character selection from now on!");
                                                torf[3]=true;
                                                data[60]-=500;
                                            }
                                            else if(names[55].equals("2"))
                                            {
                                                System.out.println(SEP+"CONGRATULATIONS! You just purchased Sensei with 500 sheckles! You can select it in character selection from now on!");
                                                torf[4]=true;
                                                data[60]-=500;
                                            }
                                            else if(names[55].equals("3"))
                                            {
                                                System.out.println(SEP+"CONGRATULATIONS! You just purchased Magician with 500 sheckles! You can select it in character selection from now on!");
                                                torf[5]=true;
                                                data[60]-=500;
                                            }
                                            System.out.println(SEP+"Press anything to return to character purchasing page.");
                                            kb.nextLine();
                                        }
                                    }
                                }
                            }
                        }
                        else if(names[54].equals("2"))//armors
                        {
                            while(true)
                            {
                                System.out.println(SEP+"Welcome to armors, enter 1 to check out your armor stats, enter 2 for upgrading, enter 3 to return to market page.");
                                names[57]=kb.nextLine();
                                while(!names[57].equals("1")&&!names[57].equals("2")&&!names[57].equals("3"))
                                {
                                    System.out.println("Invalid entry...\nEnter 1 to check out your armor stats, enter 2 for upgrading, enter 3 to return to market page.");
                                    names[57]=kb.nextLine();
                                }    
                                if(names[57].equals("1"))//just checking their armor stats
                                {
                                    System.out.println("Here are you armors:\n"+SEP+"the Crown of Azur & Crimson:");
                                    if(!torf[6]&&!torf[7]&&!torf[8]&&!torf[9])
                                        System.out.println("You haven't unlocked the Crown of Azur & Crimson, "+name+"...");
                                    else
                                    {
                                        if(torf[6])
                                            System.out.println("[Level 1, +5% health bonus activated]");
                                        else if(torf[7])
                                            System.out.println("[Level 2, +10% health bonus activated]");
                                        else if(torf[8])
                                            System.out.println("[Level 3, +15% health bonus activated]");
                                        else if(torf[9])
                                            System.out.println("[Max level, +20% health bonus activated]");
                                    }
                                    System.out.println(SEP+"Impera:");
                                    if(!torf[10]&&!torf[11]&&!torf[12]&&!torf[13])
                                        System.out.println("You haven't unlocked Impera, "+name+"...");    
                                    else
                                    {    
                                        if(torf[10])
                                            System.out.println("[Level 1, +5% damage bonus activated]");
                                        else if(torf[11])
                                            System.out.println("[Level 2, +10% damage bonus activated]");
                                        else if(torf[12])
                                            System.out.println("[Level 3, +15% damage bonus activated]");
                                        else if(torf[13])
                                            System.out.println("[Max level, +20% damage bonus activated]");
                                    }
                                    System.out.println(SEP+"Aetherion:");
                                    if(!torf[14]&&!torf[15]&&!torf[16]&&!torf[17])
                                        System.out.println("You haven't unlocked Aetherion, "+name+"...");    
                                    else
                                    {    
                                        if(torf[14])
                                            System.out.println("[Level 1, 5% less damage taken activated]");
                                        else if(torf[15])
                                            System.out.println("[Level 2, 10% less damage taken activated]");
                                        else if(torf[16])
                                            System.out.println("[Level 3, 15% less damage taken activated]");
                                        else if(torf[17])
                                            System.out.println("[Max level, 20% less damage taken activated]");
                                    }
                                    System.out.println(SEP+"Press anything to return to armor page.");
                                    kb.nextLine();
                                }
                                else if(names[57].equals("2"))//actually purchasing the upgrades
                                {    
                                    while(true)
                                    {    
                                        names[56]="";
                                        System.out.println(SEP+"You currently have "+data[60]+" sheckles.\nEach upgrade requires 100 sheckles.");
                                        if(data[60]<100)
                                        {
                                            System.out.println("You don't have enough sheckles to do any armor upgrading/unlocking...\n"+SEP+"Press anything to return to armor page.");
                                            kb.nextLine();
                                            break;
                                        }
                                        else
                                        {
                                            System.out.println("Choose which armor to upgrade/unlock, "+name+".\n"+SEP+"1 for the Crown of Azur & Crimson: ");
                                            if(!torf[6]&&!torf[7]&&!torf[8]&&!torf[9])
                                                System.out.println("You haven't unlocked the Crown of Azur & Crimson, "+name+"...");
                                            else
                                            {
                                                if(torf[6])
                                                    System.out.println("[Level 1, +5% health bonus activated]");
                                                else if(torf[7])
                                                    System.out.println("[Level 2, +10% health bonus activated]");
                                                else if(torf[8])
                                                    System.out.println("[Level 3, +15% health bonus activated]");
                                                else if(torf[9])
                                                    System.out.println("[Max level, +20% health bonus activated]");
                                            }
                                            System.out.println(SEP+"2 for Impera: ");
                                            if(!torf[10]&&!torf[11]&&!torf[12]&&!torf[13])
                                                System.out.println("You haven't unlocked Impera, "+name+"...");    
                                            else
                                            {    
                                                if(torf[10])
                                                    System.out.println("[Level 1, +5% damage bonus activated]");
                                                else if(torf[11])
                                                    System.out.println("[Level 2, +10% damage bonus activated]");
                                                else if(torf[12])
                                                    System.out.println("[Level 3, +15% damage bonus activated]");
                                                else if(torf[13])
                                                    System.out.println("[Max level, +20% damage bonus activated]");
                                            }
                                            System.out.println(SEP+"3 for Aetherion: ");
                                            if(!torf[14]&&!torf[15]&&!torf[16]&&!torf[17])
                                                System.out.println("You haven't unlocked Aetherion, "+name+"...");    
                                            else
                                            {    
                                                if(torf[14])
                                                    System.out.println("[Level 1, 5% less damage taken activated]");
                                                else if(torf[15])
                                                    System.out.println("[Level 2, 10% less damage taken activated]");
                                                else if(torf[16])
                                                    System.out.println("[Level 3, 15% less damage taken activated]");
                                                else if(torf[17])
                                                    System.out.println("[Max level, 20% less damage taken activated]");
                                            }
                                            System.out.println(SEP+"Enter 4 to return to armor page.");
                                            names[58]=kb.nextLine();
                                            while(!names[58].equals("1")&&!names[58].equals("2")&&!names[58].equals("3")&&!names[58].equals("4"))
                                            {
                                                System.out.println("Invalid entry...\nChoose which armor to upgrade/unlock, "+name+"1 for Crown of Azur & Crimson, 2 for Impera, 3 for Aetherion. 4 to return to armor page.");
                                                names[58]=kb.nextLine();
                                            }  
                                            if(names[58].equals("1"))//the crown
                                            {
                                                if(!torf[6]&&!torf[7]&&!torf[8]&&!torf[9])
                                                {
                                                    System.out.println(SEP+"To unlock the Crown of Azur & Crimson, you need 100 sheckles,it will provide you with +5% health bonus each upgrade.\nDo you want to purchase the Crown of Azur & Crimson? Enter y for yes, n for no to cancel.");
                                                    names[56]=kb.nextLine();
                                                    while(!names[56].equals("y")&&!names[56].equals("n"))
                                                    {
                                                        System.out.println("Invalid entry...\nEnter y for yes, n for no to cancel.");
                                                        names[56]=kb.nextLine();
                                                    }
                                                    if(names[56].equals("y"))
                                                    {
                                                        System.out.println("CONGRATULATIONS! You just unlocked the Crown of Azur & Crimson with 100 sheckles, it is set to level 1! You will have a permanent +5% health bonus from now on!");
                                                        torf[6]=true;//lvl 1 upgrade +5% health bonus
                                                        data[60]-=100;
                                                    }
                                                }
                                                else if(torf[6]&&!torf[7])
                                                {
                                                    System.out.println(SEP+"To upgrade the Crown of Azur & Crimson to level 2, you need 100 sheckles, it will provide you with +10% health bonus.\nDo you want to upgrade the Crown of Azur & Crimson to level 2? Enter y for yes, n for no to return to cancel.");
                                                    names[56]=kb.nextLine();
                                                    while(!names[56].equals("y")&&!names[56].equals("n"))
                                                    {
                                                        System.out.println("Invalid entry...\nEnter y for yes, n for no to cancel.");
                                                        names[56]=kb.nextLine();
                                                    }
                                                    if(names[56].equals("y"))
                                                    {
                                                        System.out.println("CONGRATULATIONS! You just upgraded the Crown of Azur & Crimson to level 2 with 100 sheckles! You will have a permanent +10% health bonus from now on!");
                                                        torf[6]=false;
                                                        torf[7]=true;//lvl 2 upgrade +10% health bonus
                                                        data[60]-=100;
                                                    }
                                                }
                                                else if(torf[7]&&!torf[8])
                                                {
                                                    System.out.println(SEP+"To upgrade the Crown of Azur & Crimson to level 3, you need 100 sheckles, it will provide you with +15% health bonus.\nDo you want to upgrade the Crown of Azur & Crimson to level 3? Enter y for yes, n for no to cancel.");
                                                    names[56]=kb.nextLine();
                                                    while(!names[56].equals("y")&&!names[56].equals("n"))
                                                    {
                                                        System.out.println("Invalid entry...\nEnter y for yes, n for no to cancel.");
                                                        names[56]=kb.nextLine();
                                                    }
                                                    if(names[56].equals("y"))
                                                    {
                                                        System.out.println("CONGRATULATIONS! You just upgraded the Crown of Azur & Crimson to level 3 with 100 sheckles! You will have a permanent +15% health bonus from now on!");
                                                        torf[7]=false;
                                                        torf[8]=true;//lvl 3 upgrade +15% health bonus 
                                                        data[60]-=100;
                                                    }
                                                }
                                                else if(torf[8]&&!torf[9])
                                                {
                                                    System.out.println(SEP+"To upgrade the Crown of Azur & Crimson to the max level, you need 100 sheckles, it will provide you with +20% health bonus.\nDo you want to upgrade the Crown of Azur & Crimson to the max level? Enter y for yes, n for no to cancel.");
                                                    names[56]=kb.nextLine();
                                                    while(!names[56].equals("y")&&!names[56].equals("n"))
                                                    {
                                                        System.out.println("Invalid entry...\nEnter y for yes, n for no to cancel.");
                                                        names[56]=kb.nextLine();
                                                    }
                                                    if(names[56].equals("y"))
                                                    {
                                                        System.out.println("CONGRATULATIONS! You just upgraded the Crown of Azur & Crimson to the max level with 100 sheckles! You will have a permanent +20% health bonus from now on!");
                                                        torf[8]=false;
                                                        torf[9]=true;//lvl 4 upgrade +20% health bonus
                                                        data[60]-=100;
                                                    }
                                                }
                                                else if(torf[9])
                                                {
                                                    System.out.println(SEP+"Your Crown of Azur & Crimson is already at max level! Press any key to return.");
                                                    kb.nextLine();
                                                }
                                                if(names[56].equals("n"))
                                                {
                                                    System.out.println(SEP+"Cancelling...\nPress anything to return.");
                                                    kb.nextLine();
                                                }
                                            }
                                            else if(names[58].equals("2"))//impera
                                            {
                                                if(!torf[10]&&!torf[11]&&!torf[12]&&!torf[13])
                                                {
                                                    System.out.println(SEP+"To unlock Impera, you need 100 sheckles,it will provide you with +5% damage bonus each upgrade.\nDo you want to purchase Impera? Enter y for yes, n for no to cancel.");
                                                    names[56]=kb.nextLine();
                                                    while(!names[56].equals("y")&&!names[56].equals("n"))
                                                    {
                                                        System.out.println("Invalid entry...\nEnter y for yes, n for no to cancel.");
                                                        names[56]=kb.nextLine();
                                                    }
                                                    if(names[56].equals("y"))
                                                    {
                                                        System.out.println("CONGRATULATIONS! You just unlocked Impera with 100 sheckles, it is set to level 1! You will have a permanent +5% damage bonus from now on!");
                                                        torf[10]=true;//lvl 1 upgrade +5% damage bonus
                                                        data[60]-=100;
                                                    }
                                                }
                                                else if(torf[10]&&!torf[11])
                                                {
                                                    System.out.println(SEP+"To upgrade Impera to level 2, you need 100 sheckles, it will provide you with +10% damage bonus.\nDo you want to upgrade Impera to level 2? Enter y for yes, n for no to cancel.");
                                                    names[56]=kb.nextLine();
                                                    while(!names[56].equals("y")&&!names[56].equals("n"))
                                                    {
                                                        System.out.println("Invalid entry...\nEnter y for yes, n for no to cancel.");
                                                        names[56]=kb.nextLine();
                                                    }
                                                    if(names[56].equals("y"))
                                                    {
                                                        System.out.println("CONGRATULATIONS! You just upgraded Impera to level 2 with 100 sheckles! You will have a permanent +10% damage bonus from now on!");
                                                        torf[10]=false;
                                                        torf[11]=true;//lvl 2 upgrade +10% damage bonus
                                                        data[60]-=100;
                                                    }
                                                }
                                                else if(torf[11]&&!torf[12])
                                                {
                                                    System.out.println(SEP+"To upgrade Impera to level 3, you need 100 sheckles, it will provide you with +15% damage bonus.\nDo you want to upgrade Impera to level 3? Enter y for yes, n for no to cancel.");
                                                    names[56]=kb.nextLine();
                                                    while(!names[56].equals("y")&&!names[56].equals("n"))
                                                    {
                                                        System.out.println("Invalid entry...\nEnter y for yes, n for no to cancel.");
                                                        names[56]=kb.nextLine();
                                                    }
                                                    if(names[56].equals("y"))
                                                    {
                                                        System.out.println("CONGRATULATIONS! You just upgraded Impera to level 3 with 100 sheckles! You will have a permanent +15% damage bonus from now on!");
                                                        torf[11]=false;
                                                        torf[12]=true;//lvl 3 upgrade +15% damage bonus
                                                        data[60]-=100;
                                                    }
                                                }
                                                else if(torf[12]&&!torf[13])
                                                {
                                                    System.out.println(SEP+"To upgrade Impera to the max level, you need 100 sheckles, it will provide you with +20% damage bonus.\nDo you want to upgrade Impera to the max level? Enter y for yes, n for no to return to cancel.");
                                                    names[56]=kb.nextLine();
                                                    while(!names[56].equals("y")&&!names[56].equals("n"))
                                                    {
                                                        System.out.println("Invalid entry...\nEnter y for yes, n for no to return to cancel.");
                                                        names[56]=kb.nextLine();
                                                    }
                                                    if(names[56].equals("y"))
                                                    {
                                                        System.out.println("CONGRATULATIONS! You just upgraded Impera to the max level with 100 sheckles! You will have a permanent +20% damage bonus from now on!");
                                                        torf[12]=false;
                                                        torf[13]=true;//lvl 4 upgrade +20% damage bonus
                                                        data[60]-=100;
                                                    }
                                                }
                                                else if(torf[13])
                                                {
                                                    System.out.println(SEP+"Your Impera is already at max level! Press any key to return.");
                                                    kb.nextLine();
                                                }
                                                if(names[56].equals("n"))
                                                {
                                                    System.out.println(SEP+"Cancelling...\nPress anything to return.");
                                                    kb.nextLine();
                                                }
                                            }
                                            else if(names[58].equals("3"))//aetherion
                                            {
                                                if(!torf[14]&&!torf[15]&&!torf[16]&&!torf[17])
                                                {
                                                    System.out.println(SEP+"To unlock Aetherion, you need 100 sheckles,it will provide you with 5% less damage taken each upgrade.\nDo you want to purchase Aetherion? Enter y for yes, n for no to cancel.");
                                                    names[56]=kb.nextLine();
                                                    while(!names[56].equals("y")&&!names[56].equals("n"))
                                                    {
                                                        System.out.println("Invalid entry...\nEnter y for yes, n for no to return to cancel.");
                                                        names[56]=kb.nextLine();
                                                    }
                                                    if(names[56].equals("y"))
                                                    {
                                                        System.out.println("CONGRATULATIONS! You just unlocked Aetherion with 100 sheckles, it is set to level 1! You will have permanent 5% less damage taken from now on!");
                                                        torf[14]=true;//lvl 1 upgrade 5% less damage taken
                                                        data[60]-=100;
                                                    }
                                                }
                                                else if(torf[14]&&!torf[15])
                                                {
                                                    System.out.println(SEP+"To upgrade Aetherion to level 2, you need 100 sheckles, it will provide you with 10% less damage taken.\nDo you want to upgrade Aetherion to level 2? Enter y for yes, n for no to return to cancel.");
                                                    names[56]=kb.nextLine();
                                                    while(!names[56].equals("y")&&!names[56].equals("n"))
                                                    {
                                                        System.out.println("Invalid entry...\nEnter y for yes, n for no to return to cancel.");
                                                        names[56]=kb.nextLine();
                                                    }
                                                    if(names[56].equals("y"))
                                                    {
                                                        System.out.println("CONGRATULATIONS! You just upgraded Aetherion to level 2 with 100 sheckles! You will have permanent +10% less damage taken from now on!");
                                                        torf[14]=false;
                                                        torf[15]=true;//lvl 2 upgrade 10% less damage taken
                                                        data[60]-=100;
                                                    }
                                                }
                                                else if(torf[15]&&!torf[16])
                                                {
                                                    System.out.println(SEP+"To upgrade Aetherion to level 3, you need 100 sheckles, it will provide you with 15% less damage taken.\nDo you want to upgrade Aetherion to level 3? Enter y for yes, n for no to return to cancel.");
                                                    names[56]=kb.nextLine();
                                                    while(!names[56].equals("y")&&!names[56].equals("n"))
                                                    {
                                                        System.out.println("Invalid entry...\nEnter y for yes, n for no to return to cancel.");
                                                        names[56]=kb.nextLine();
                                                    }
                                                    if(names[56].equals("y"))
                                                    {
                                                        System.out.println("CONGRATULATIONS! You just upgraded Aetherion to level 3 with 100 sheckles! You will have permanent 15% less damage taken from now on!");
                                                        torf[15]=false;
                                                        torf[16]=true;//lvl 3 upgrade 15% less damage taken
                                                        data[60]-=100;
                                                    }
                                                }
                                                else if(torf[16]&&!torf[17])
                                                {
                                                    System.out.println(SEP+"To upgrade Aetherion to the max level, you need 100 sheckles, it will provide you with 20% less damage taken.\nDo you want to upgrade Aetherion to the max level? Enter y for yes, n for no to cancel.");
                                                    names[56]=kb.nextLine();
                                                    while(!names[56].equals("y")&&!names[56].equals("n"))
                                                    {
                                                        System.out.println("Invalid entry...\nEnter y for yes, n for no to cancel.");
                                                        names[56]=kb.nextLine();
                                                    }
                                                    if(names[56].equals("y"))
                                                    {
                                                        System.out.println("CONGRATULATIONS! You just upgraded Aetherion to the max level with 100 sheckles! You will have permanent 20% less damage taken from now on!");
                                                        torf[16]=false;
                                                        torf[17]=true;//lvl 4 upgrade 20% less damage taken
                                                        data[60]-=100;
                                                    }
                                                }
                                                else if(torf[17])
                                                {
                                                    System.out.println(SEP+"Your Aetherion is already at max level! Press any key to return.");
                                                    kb.nextLine();
                                                }
                                                if(names[56].equals("n"))
                                                {
                                                    System.out.println(SEP+"Cancelling...\nPress anything to return.");
                                                    kb.nextLine();
                                                }
                                            }
                                            else //returning to armor page
                                                break;
                                        }
                                    }
                                }
                                else //returning to market page
                                    break;
                            }
                        }
                        else if(names[54].equals("3"))//intended for potions
                        {
                            System.out.println("Sorry, but potion feature is not developed, press anything to return to market page.");
                            kb.nextLine();
                        }
                        else //returning to home menu
                            break;
                    }
                }
                else if(gameState==4) //exiting the game
                {
                    System.out.println(SEP+"Thank you for playing, you were a heck of a fighter, "+name+"! See you!");                        
                    System.exit(0);
                    break;
                }
            }
        }
    }
    public static int[] fighting(String Choice, String chrct, String opp, String[] names, int[] data, boolean[]torf)//handles fighting contexts, choices
    {   
        Scanner kb=new Scanner(System.in);
        Random rand=new Random();
        String SEP = "------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------\n";
        boolean playerDodges=false,opponentDodges=false,opppowerup=false,stun=false,oppstun=false,stunRound=false,oppstunround=false,buffround=false,oppbuffround=false,buffavoidstun=false,oppbuffavoidstun=false,instakill=false;
        data[50]=0/*used to track rounds that player is buffed*/;
        data[51]=0/*used to track rounds that opponent is buffed*/;
        if(torf[6])//lvl 1 crown
        {
            data[0]=(int)Math.round(data[0]*1.05);
            System.out.println(SEP+"[The Crown of Azur & Crimson effect on, +5% health bonus for "+chrct+"!]");
        }
        else if(torf[7])//lvl 2 crown
        {
            data[0]=(int)Math.round(data[0]*1.1);
            System.out.println(SEP+"[The Crown of Azur & Crimson effect on, +10% health bonus for "+chrct+"!]");
        }
        else if(torf[8])//lvl 3 crown
        {
            data[0]=(int)Math.round(data[0]*1.15);
            System.out.println(SEP+"[The Crown of Azur & Crimson effect on, +15% health bonus for "+chrct+"!]");
        }
        else if(torf[9])//max level crown
        {
            data[0]=(int)Math.round(data[0]*1.2);
            System.out.println(SEP+"[The Crown of Azur & Crimson effect on, +20% health bonus for "+chrct+"!]");
        }
        data[40]=data[0];//used to track player's health percentage during battle
        data[44]=data[1];//used to check player's original max stamina
        data[41]=data[10];//using a second data to track the original hp of the opp for later uses, as it varies a lot from opponent to opponent
        data[45]=data[11];//using a second data to track the original stamina of the opp for later uses, as it varies from opponent to opponent
        for(int i=0;true;i++)//basically as a perpetually true statement
        {
            // reset dodge flags each round
            playerDodges=false;
            opponentDodges=false;
            opppowerup=false;
            buffavoidstun=false;
            oppbuffavoidstun=false;
            String opt="",aopt="",oaopt="";
            int admg=0,oadmg=0,astc=0,oastc=0,optstc=0,oppopt=0,choice=0;
            //damage, stamina cost, and option stamina costs for both sides,and player choice of action
            if(!torf[0])//tutorial fight
            {
                System.out.println(SEP+"TUTORIAL STEP 1: Use your basic attack to learn how attacking works.\nPress 1 to use "+names[0]+".");
                opt=kb.nextLine();
                while(!opt.equals("1"))
                {
                    System.out.println("Invalid entry... Press 1 to attack with "+names[0]+".");
                    opt=kb.nextLine();
                }
                // player attack resolves
                aopt=names[0];
                admg=data[2];
                astc=data[3];
                data[10]-=damage(false,admg);
                data[1]-=stamina(astc);
                // Pochita basic attack
                oaopt=names[4];
                oadmg=data[12];
                oastc=data[13];
                data[11]-=stamina(oastc);
                data[0]-=damage(false,oadmg);
                System.out.println(SEP+chrct+" spent "+stamina(astc)+" stamina, and used "+aopt+", and dealt "+damage(false,admg)+" damage.");
                System.out.println("Pochita spent "+stamina(oastc)+" stamina, and used "+oaopt+", and dealt "+damage(false,oadmg)+" damage to you.");
                System.out.println("Press any key to continue...");
                kb.nextLine();// Step 2: Dodge demonstration — force a successful dodge so player experiences it
                System.out.println(SEP+"TUTORIAL STEP 2: Now try dodging. Press 2 to attempt a dodge.");
                opt=kb.nextLine();
                while(!opt.equals("2"))
                {
                    System.out.println("Invalid entry... Press 2 to attempt a dodge.");
                    opt=kb.nextLine();
                }
                // simulate dodge success for teaching purposes
                playerDodges=true;
                System.out.println(SEP+chrct+" attempted to dodge.");
                System.out.println(chrct+"'s dodge attempt was successful, ignoring all impact this round.");
                // Pochita attacks but dodge avoids damage
                oaopt=names[4];
                oadmg=data[12];
                oastc=data[13];
                data[11]-=stamina(oastc);
                System.out.println("Pochita spent "+stamina(oastc)+" stamina, and used "+oaopt+". However, your dodge succeeded and you took no damage.");
                System.out.println("Press any key to continue...");
                kb.nextLine();// Step 3: Pochita buffs itself to demonstrate buff
                System.out.println(SEP+"TUTORIAL STEP 3: Pochita is about to buff itself. Observe the buff behavior.\nPochita used "+names[7]+" to buff!");
                oppbuffround=true;
                data[51]=1; // indicate buff just started
                System.out.println(SEP+"[Pochita's buff is active — its next attack will be stronger.]");
                System.out.println("Press any key to continue...");
                kb.nextLine();// Step 4: Player attacks, then Pochita uses stun this same round while player is instructed to shield next
                System.out.println(SEP+"TUTORIAL STEP 4: Attack again, then watch as Pochita attempts to stun you. Press 1 to attack.");
                opt=kb.nextLine();
                while(!opt.equals("1"))
                {
                    System.out.println("Invalid entry... Press 1 to attack.");
                    opt=kb.nextLine();
                }
                // player attack resolves
                aopt=names[0];
                admg=data[2];
                astc=data[3];
                data[10]-=damage(false,admg);
                data[1]-=stamina(astc);
                System.out.println(SEP+chrct+" spent "+stamina(astc)+" stamina, and used "+aopt+", and dealt "+damage(false,admg)+" damage.");
                // Pochita attempts to stun this round (use names[6] -> Playful Stun)
                oaopt=names[6];
                oadmg=data[16];
                oastc=data[17];
                data[11]-=stamina(oastc);
                if(oppbuffround) oadmg=(int)Math.round(oadmg*1.25);
                data[0]-=damage(false,oadmg);
                if(!playerDodges) stun=true;
                System.out.println("Pochita spent "+stamina(oastc)+" stamina, and used "+oaopt+", and dealt "+damage(false,oadmg)+" damage.");
                if(stun) System.out.println("OH NO! Pochita's "+oaopt+" will stun you and prevent actions next round if not cancelled.");
                System.out.println("Press any key to continue to the next demonstration (you will be asked to shield now)...");
                kb.nextLine();// Step 5: Player shields but shield does not prevent stun next round
                System.out.println(SEP+"TUTORIAL STEP 5: Try shielding this round to see how it interacts with stun. Press 0 to shield.");
                opt=kb.nextLine();
                while(!opt.equals("0"))
                {
                    System.out.println("Invalid entry... Press 0 to shield.");
                    opt=kb.nextLine();
                }
                aopt="shield";
                astc=0;
                System.out.println(SEP+chrct+" shielded.");
                oaopt=names[4];
                oadmg=data[12];
                oastc=data[13];
                data[11]-=stamina(oastc);
                data[0]-=damage(true,oadmg);
                System.out.println("Pochita spent "+stamina(oastc)+" stamina, and used "+oaopt+", and dealt "+damage(true,oadmg)+" damage (halved by shield).");
                if(stun)
                {
                    stunRound=true;
                    System.out.println(SEP+"Notice: Your shield reduced this round's damage, but it does NOT prevent the stun effect that Pochita applied. You will be unable to act in the next round.");
                }
                System.out.println("Press any key to continue...");
                kb.nextLine();// Simulate the stunned round
                if(stunRound)
                {
                    System.out.println(SEP+"TUTORIAL: You are stunned and cannot take actions this round. Press any key to confirm.");
                    oppopt=1;
                    oaopt=names[4];
                    oadmg=data[12];
                    oastc=data[13];
                    data[11]-=stamina(oastc);
                    data[0]-=damage(false,oadmg);
                    System.out.println("Pochita spent "+stamina(oastc)+" stamina, and used "+oaopt+", and dealt "+damage(false,oadmg)+" damage while you were stunned.");
                    stunRound=false;
                    stun=false;
                    System.out.println("Press any key to continue...");
                    kb.nextLine();
                }
                // Final Step: use best attack
                System.out.println(SEP+"FINAL STEP: Use your best available attack now to finish the tutorial. Press 1 to use "+names[0]+".");
                opt=kb.nextLine();
                while(!opt.equals("1")&&!opt.equals("3"))
                {
                    System.out.println("Invalid entry... Press 1 to use "+names[0]+".");
                    opt=kb.nextLine();
                }
                aopt=names[0];
                admg=data[2];
                astc=data[3];
                data[10]-=damage(false,admg);
                data[1]-=stamina(astc);
                System.out.println(SEP+chrct+" spent "+stamina(astc)+" stamina, and used "+aopt+", and dealt "+damage(false,admg)+" damage.");
                return data;
            }
            if(buffround&&data[50]==1&&data[0]<625)//player buff healing 10% health, top at max hp
            {
                data[0]+=(int)Math.round(0.1*data[40]);
                if(data[0]>625)
                    data[0]=625;
            }
            if(oppbuffround&&data[51]==1)//opp buff
            {
                if(opp.equals("Goblin")&&data[10]<(int)Math.round(0.5*data[41]))//dooubles hp for goblin, top at 50% of max hp
                {
                    data[10]*=2;
                    if(data[10]>(int)Math.round(0.5*data[41]))
                        data[10]=(int)Math.round(0.5*data[41]);
                }
                else if(opp.equals("Clanka"))//clanka buff healing 10% health, top at max hp
                {
                    data[10]+=(int)Math.round(0.1*data[41]);
                    if(data[10]>data[41])
                        data[10]=data[41];
                }
            }
            // At the start of each round
            if(data[50]>4)//to ensure buff is only 3 round after the buff super activation round
            {
                buffround=false;
                data[50]=0;
                System.out.println(SEP+chrct+"'s buff has ended.");
            }
            if(data[51]>4)
            {
                oppbuffround=false;
                data[51]=0;
                System.out.println(SEP+opp+"'s buff has ended.");
            }
            if(buffround)
            {
                if(data[50]==1)
                    System.out.println(SEP+"Your innate hitman is awakened for the next 3 rounds! You healed 10% health(capped at max 625), will deal 25% more damage, and your stamina regenerated each round is now 2 instead of 1.\n"+opp+" deals 25% less damage to you, and you have a 50% chance to avoid the effects from "+opp+"'s attack.");
                else if(data[50]>1&&data[50]<4)
                    System.out.println(SEP+"[Hitman Awaken Active: +25% dmg, 25% dmg reduction, +50% dodge]");
                if(stunRound)
                {
                    if(rand.nextInt(2)==0&&data[50]>=1&&data[50]<4)
                        buffavoidstun=true;
                    if(buffavoidstun)
                    {
                        System.out.println("LUCKY YOU! "+opp+" took away you ability to perform actions.\nBut, empowered by your inner hitman aura, you resisted the effect!\nYou get to act normally this round.");
                        stunRound=false;
                    }
                    else if(!buffavoidstun)
                        System.out.println("OOPS! Even your inner hitman power wasn't enough to protect you from "+opp+"'s previous attack effect.");
                }
                if(data[1]<8)//sensei
                {
                    data[1]+=2;
                    if(data[1]>8)
                        data[1]=8;
                }
            }
            else if(!buffround)
            {
                if (data[1]<data[44])//the stamina system for player that recovers 1 point of stamina per loop unless max stamina is reached
                {
                    ++data[1];
                    if(data[1]>data[44])
                        data[1]=data[44];
                }
            }
            if(oppbuffround)
            {
                if(data[51]==1)
                {
                    if(opp.equals("Goblin"))
                        System.out.println(SEP+opp+" screeches as its body swells with brute strength!\n"+"The Goblin mutates into a Goblin Giant — dumb, massive, and hard to put down.\nThe goblin giant doubles its health if it gets below 50% (caps at 50% of max hp)\nThe giant does 25% less damage, but takes 25% damage from "+chrct+".\nIts stamina regenerated each round is now 2 instead of 1, and there is 50% chance to avoid the effects from "+chrct+"'s attack.\nThe chances of it gaining a powerup and doing double the damage is now raised from 5% to 25%.\nThe effect lasts for 3 rounds after the round the super is activated");                
                    else 
                        System.out.println(SEP+opp+" whirs to life with the clang of hyper‑machinery!\nThis robotic behemoth — half Mega Knight savage stomp, half P.E.K.K.A devastator — transcends flesh and steel.\nThe crowd whispers the meme‑name with equal parts awe and dread: Clanka, the Clanker King!\nThe buffed Clanka heals 10% of its health (caps at max hp)\nIt does 25% more damage, and takes 25% damage from "+chrct+".\nIts stamina regenerated each round is now 2 instead of 1, and there is 50% chance to avoid the effects from "+chrct+"'s attack.\nThe chances of it gaining a powerup and doing double the damage is now raised from 5% to 25%.\nThe effect lasts for 3 rounds after the round the super is activated.");
                }
                else if(data[51]>1&&data[51]<=4)
                {
                    if(opp.equals("Goblin"))
                        System.out.println(SEP+"[Goblin Giant Active -25% dmg, 25% player dmg reduction, +50% dodge, 25% chance of powerup]");
                    else
                        System.out.println(SEP+"[Clanka Overclock Active +25% dmg, 25% player dmg reduction, +50% dodge, 25% chance of powerup]");
                }
                if(oppstunround)
                {
                    if(rand.nextInt(2)==0&&data[51]>=1&&data[51]<4)
                        oppbuffavoidstun=true;
                    if(oppbuffavoidstun)
                    {
                        if(opp.equals("Goblin")) 
                            System.out.println(opp+" powers through like a charging Goblin Giant!\nIt ignored "+chrct+"'s attack effect, and will still be able to perform actions this round.");
                        else
                            System.out.println(opp+" refuses to be dazed, its meme‑love of ‘clanker chaos’ keeping it locked in!\nIt ignored "+chrct+"'s attack effect, and will still be able to perform actions this round.");
                        oppstunround=false;
                    }
                    else if(!oppbuffavoidstun)
                        System.out.println("OOPS! Even "+opp+"'s buffed might wasn't enough to protect it from "+chrct+"'s attack effect.");
                }
                if(data[11]<data[45])
                {
                    data[11]+=2;
                    if(data[11]>data[45])
                        data[11]=data[45];
                }
            }
            else if(!oppbuffround)
            {  
                if (data[11]<data[45])//the stamina system for opponent that recovers 1 point of stamina per loop unless max stamina is reached
                {
                    ++data[11];
                    if(data[11]>data[45])
                        data[11]=data[45];
                }
            }
            data[42]=(int)Math.round((data[0]*100.0)/data[40]);//player health percentage
            data[43]=(int)Math.round((data[10]*100.0)/data[41]);//opponent health percentage
            System.out.println(SEP+"Round Status:\n"+chrct+"\nHealth: "+data[0]+" ("+data[42]+ "%)\nStamina: "+data[1]+"\n"+opp+"\nHealth: "+data[10]+" ("+data[43]+"%)\nStamina: "+data[11]);
            if(oppbuffround&&!oppstunround)
            {
                if(rand.nextInt(4)==0)//multiplier of a 25% chance for the opponent to do twice as much damage when buffed
                {
                    opppowerup=true;
                    System.out.println(SEP+"Oh no! The "+opp+" gained a powerup! Its damage this round is doubled!");
                }
            }
            else if(!oppbuffround&&!oppstunround)
            {
                if(rand.nextInt(20)==0)//multiplier of a 5% chance for the opponent to do twice as much damage
                {
                    opppowerup=true;
                    System.out.println(SEP+"Oh no! The "+opp+" gained a powerup! Its damage this round is doubled!");
                }
            }
            // Indicating moves available based on player's progression and unavailable moves based on stamina.
            if(!stunRound)
            {
                if((Choice.equals("1")&&data[23]>=3)||(Choice.equals("2")&&data[24]>=3)||(Choice.equals("3")&&data[25]>=3)) //when player unlocked every move
                {
                    if(data[1]>=data[9]) // enough stamina for everything
                    {
                        System.out.println(SEP+"Please choose your action of the round: 0 for shield, 1 for "+names[0]+", 2 for dodge, 3 for "+names[1]+", 4 for "+names[2]+", 5 for "+names[3]+".");
                        opt=kb.nextLine();
                        while(!opt.equals("0")&&!opt.equals("1")&&!opt.equals("2")&&!opt.equals("3")&&!opt.equals("4")&&!opt.equals("5"))
                        {
                            System.out.println("Invalid choice of action!\nPlease re-choose your action of the round: 0 for shield, 1 for "+names[0]+", 2 for dodge, 3 for "+names[1]+", 4 for "+names[2]+", 5 for "+names[3]+".");
                            opt=kb.nextLine();
                        }
                    }
                    else if(data[1]>=data[7]) // can do 0-4
                    {
                        System.out.println(SEP+"Please choose your action of the round: 0 for shield, 1 for "+names[0]+", 2 for dodge, 3 for "+names[1]+", 4 for "+names[2]+". You don't have enough stamina for "+names[3]+".");
                        opt=kb.nextLine();
                        while(!opt.equals("0")&&!opt.equals("1")&&!opt.equals("2")&&!opt.equals("3")&&!opt.equals("4"))
                        {
                            System.out.println("Invalid choice of action!\nPlease re-choose your action of the round: 0 for shield, 1 for "+names[0]+", 2 for dodge, 3 for "+names[1]+", 4 for "+names[2]+". You don't have enough stamina for "+names[3]+".");
                            opt=kb.nextLine();
                        }
                    }
                    else if(data[1]>=data[5]) // can do 0-3
                    {
                        System.out.println(SEP+"Please choose your action of the round: 0 for shield, 1 for "+names[0]+", 2 for dodge, 3 for "+names[1]+". You don't have enough stamina for "+names[2]+" or "+names[3]+".");
                        opt=kb.nextLine();
                        while(!opt.equals("0")&&!opt.equals("1")&&!opt.equals("2")&&!opt.equals("3"))
                        {
                            System.out.println("Invalid choice of action!\nPlease re-choose your action of the round: 0 for shield, 1 for "+names[0]+", 2 for dodge, 3 for "+names[1]+". You don't have enough stamina for "+names[2]+" or "+names[3]+".");
                            opt=kb.nextLine();
                        }
                    }
                    else // can only do 0-2
                    {
                        System.out.println(SEP+"Please choose your action of the round: 0 for shield, 1 for "+names[0]+", 2 for dodge. You don't have enough stamina for "+names[1]+", "+names[2]+", or "+names[3]+".");
                        opt=kb.nextLine();
                        while(!opt.equals("0")&&!opt.equals("1")&&!opt.equals("2"))
                        {
                            System.out.println("Invalid choice of action!\nPlease re-choose your action of the round: 0 for shield, 1 for "+names[0]+", 2 for dodge. You don't have enough stamina for "+names[1]+", "+names[2]+", or "+names[3]+".");
                            opt=kb.nextLine();
                        }
                    }
                }
                else if((Choice.equals("1")&&data[23]==0)||(Choice.equals("2")&&data[24]==0)||(Choice.equals("3")&&data[25]==0)) //first round with action options being only shield, attack or dodge
                {
                    System.out.println(SEP+"Please choose your action of the round: 0 for shield, 1 for "+names[0]+", 2 for dodge.");
                    opt=kb.nextLine();
                    while(!opt.equals("0")&&!opt.equals("1")&&!opt.equals("2"))
                    {
                        System.out.println("Invalid choice of action!\nPlease re-choose your action of the round: 0 for shield, 1 for "+names[0]+", 2 for dodge.");
                        opt=kb.nextLine();
                    }
                }
                else if((Choice.equals("1")&&data[23]==1)||(Choice.equals("2")&&data[24]==1)||(Choice.equals("3")&&data[25]==1)) //after defeating the first opponent, 1 additional ability unlocked.
                {
                    if(data[1]>=data[5])
                    {
                        System.out.println(SEP+"Please choose your action of the round: 0 for shield, 1 for "+names[0]+", 2 for dodge, 3 for "+names[1]+".");
                        opt=kb.nextLine();
                        while(!opt.equals("0")&&!opt.equals("1")&&!opt.equals("2")&&!opt.equals("3"))
                        {
                            System.out.println("Invalid choice of action!\nPlease re-choose your action of the round: 0 for shield, 1 for "+names[0]+", 2 for dodge, 3 for "+names[1]+". ");
                            opt=kb.nextLine();
                        }
                    }
                    else 
                    {
                        System.out.println(SEP+"Please choose your action of the round: 0 for shield, 1 for "+names[0]+", 2 for dodge. You don't have enough stamina for "+names[1]+".");
                        opt=kb.nextLine();
                        while(!opt.equals("0")&&!opt.equals("1")&&!opt.equals("2"))
                        {
                            System.out.println("Invalid choice of action!\nPlease re-choose your action of the round: 0 for shield, 1 for "+names[0]+", 2 for dodge. You don't have enough stamina for "+names[1]+".");
                            opt=kb.nextLine();
                        }
                    }
                    // oppopt set below
                }
                else if((Choice.equals("1")&&data[23]==2)||(Choice.equals("2")&&data[24]==2)||(Choice.equals("3")&&data[25]==2)) //2 opponenets defeated with 2 addiational abilities.
                {
                    if(data[1]>=data[7])
                    {
                        System.out.println(SEP+"Please choose your action of the round: 0 for shield, 1 for "+names[0]+", 2 for dodge, 3 for "+names[1]+", 4 for "+names[2]+".");
                        opt=kb.nextLine();
                        while(!opt.equals("0")&&!opt.equals("1")&&!opt.equals("2")&&!opt.equals("3")&&!opt.equals("4"))
                        {
                            System.out.println("Invalid choice of action!\nPlease re-choose your action of the round: 0 for shield, 1 for "+names[0]+", 2 for dodge, 3 for "+names[1]+", 4 for "+names[2]+".");
                            opt=kb.nextLine();
                        }
                    }
                    else if(data[1]>=data[5]&&data[1]<data[7])
                    {
                        System.out.println(SEP+"Please choose your action of the round: 0 for shield, 1 for "+names[0]+", 2 for dodge, 3 for "+names[1]+". You don't have enough stamina for "+names[2]+".");
                        opt=kb.nextLine();
                        while(!opt.equals("0")&&!opt.equals("1")&&!opt.equals("2")&&!opt.equals("3"))
                        {
                            System.out.println("Invalid choice of action!\nPlease re-choose your action of the round: 0 for shield, 1 for "+names[0]+", 2 for dodge, 3 for "+names[1]+". You don't have enough stamina for "+names[2]+".");
                            opt=kb.nextLine();
                        }
                    }
                    else 
                    {
                        System.out.println(SEP+"Please choose your action of the round: 0 for shield, 1 for "+names[0]+", 2 for dodge. You don't have enough stamina for "+names[1]+", or "+names[2]+".");
                        opt=kb.nextLine();
                        while(!opt.equals("0")&&!opt.equals("1")&&!opt.equals("2"))
                        {
                            System.out.println("Invalid choice of action!\nPlease re-choose your action of the round: 0 for shield, 1 for "+names[0]+", 2 for dodge. You don't have enough stamina for "+names[1]+", or "+names[2]+".");
                            opt=kb.nextLine();
                        }
                    }          
                }
            }
            else if(stunRound)
            {
                System.out.println(SEP+"You are unable to take any actions this round due to impact done to you last round...");
                opt="-1";
            }
            if(!oppstunround)
            {  
                if((Choice.equals("1")&&data[23]>=3)||(Choice.equals("2")&&data[24]>=3)||(Choice.equals("3")&&data[25]>=3))// Indicating moves available for opponent based on player's progression and unavailable moves based on stamina.
                {
                    while(true)
                    {
                        if(data[11]>=data[19])
                            oppopt = rand.nextInt(6);
                        else if(data[11]>=data[17])
                            oppopt = rand.nextInt(5);
                        else if(data[11]>=data[15])
                            oppopt = rand.nextInt(4);
                        else
                            oppopt = rand.nextInt(3);
                        if(oppopt==0||oppopt==2||(oppopt==1 && data[11]>=data[13])||(oppopt==3 && data[11]>=data[15])||(oppopt==4 && data[11]>=data[17])||(oppopt==5 && data[11]>=data[19])) 
                            break;
                    }
                }
                else if((Choice.equals("1")&&data[23]==0)||(Choice.equals("2")&&data[24]==0)||(Choice.equals("3")&&data[25]==0))
                {
                    oppopt=rand.nextInt(3);
                }
                else if((Choice.equals("1")&&data[23]==1)||(Choice.equals("2")&&data[24]==1)||(Choice.equals("3")&&data[25]==1))
                {
                    if (data[11] >= data[15])
                        oppopt = rand.nextInt(4); 
                    else
                        oppopt = rand.nextInt(3); 
                }
                else if((Choice.equals("1")&&data[23]==2)||(Choice.equals("2")&&data[24]==2)||(Choice.equals("3")&&data[25]==2))
                {
                    if (data[11] >= data[17])
                        oppopt = rand.nextInt(5);
                    else if (data[11] >= data[15])
                        oppopt = rand.nextInt(4); 
                    else
                        oppopt = rand.nextInt(3); 
                }
            }
            else if(oppstunround)
            {
                System.out.println(SEP+opp+" is unable to take any actions this round due to impact done to it last round...");
                oppopt=-1;
            }
            // reading player's option and setting up the damage and stamina cost of the attack.
            if (opt.equals("0"))
            {
                aopt="shield";
                admg=0;
                astc=0;
                System.out.println(SEP+chrct+" shielded.");
            }
            else if (opt.equals("1"))
            {
                aopt=names[0];
                admg=data[2];
                astc=data[3];
            }
            else if(opt.equals("2"))
            {
                aopt="dodge";
                admg=0;
                astc=0;
                System.out.println(SEP+chrct+" attempted to dodge.");
                if(rand.nextInt(2)==0)//50% chance of successfully dodging
                {
                    playerDodges=true;
                    System.out.println(chrct+"'s dodge attempt was successful, ignoring all impact done this round.");
                }
                else
                {
                    playerDodges=false;
                    System.out.println(chrct+"'s dodge attempt failed, taking damage as normal.");
                }
            }
            else if (opt.equals("3"))
            {
                aopt=names[1];
                admg=data[4];
                astc=data[5];
            }
            else if (opt.equals("4"))
            {
                aopt=names[2];
                admg=data[6];
                astc=data[7];
                if(Choice.equals("2")&&data[10]<=(int)Math.round(data[41]*0.5))
                {
                    if(rand.nextInt(4)==0)
                    {
                        instakill=true;
                        System.out.println(SEP+chrct+" gains a chance to insta-kill with "+aopt+" if not dodged!");
                    }
                }
            }
            else if(opt.equals("5"))
            {
                aopt=names[3];
                admg=data[8];
                astc=data[9];
                if(Choice.equals("1"))
                {
                    if(rand.nextInt(20)==6)
                    {
                        instakill=true;
                        System.out.println(chrct+" gains a chance to insta-kill with "+aopt+" if not dodged!");
                    }
                }
                else if(Choice.equals("2"))
                    oppstun=true;
                else
                    buffround=true;
            }
            else if (opt.equals("-1"))
            {
                admg=0;
                astc=0;
            }
            // reading opponent option
            if (oppopt==0)
            {
                oaopt="shield";
                oadmg=0;
                oastc=0;
                if (opt.equals("0")||opt.equals("2"))
                    System.out.println(opp+" shielded itself.");                    
                else
                    System.out.println(SEP+opp+" shielded itself.");
            }
            else if (oppopt==1)
            {
                oaopt=names[4];
                oadmg=data[12];
                oastc=data[13];
            }
            else if (oppopt==2)
            {
                oaopt="dodge";
                oadmg=0;
                oastc=0;
                if (opt.equals("0")||opt.equals("2"))
                    System.out.println(opp+" attempted to dodge.");                    
                else
                    System.out.println(SEP+opp+" attempted to dodge.");
                if(rand.nextInt(2)==0)//50% chance of successfully dodging, same as for player
                {
                    opponentDodges=true;
                    System.out.println(opp+"'s dodge attempt was successful, ignoring all impact done this round.");
                }
                else
                {
                    opponentDodges=false;
                    System.out.println(opp+"'s dodge attempt failed, taking damage as normal.");
                }
            }
            else if (oppopt==3)
            {
                oaopt=names[5];
                if(opp.equals("Goblin")||opp.equals("Clanka"))//money power by goblin or pekka knight deploy by clanka to be possible for activating stun
                {
                    if(rand.nextInt(4)==2&&!playerDodges)
                    {
                        stun=true;
                    }
                }
                oadmg=data[14];
                oastc=data[15];
            }
            else if (oppopt==4)
            {
                oaopt=names[6];
                if(opp.equals("Mud Monster")||opp.equals("Clanka"))
                {
                    if(rand.nextInt(4)==2&&!playerDodges)
                    {
                        stun=true;
                    }
                }
                oadmg=data[16];
                oastc=data[17];
            }
            else if(oppopt==5)
            {
                oaopt=names[7];
                oadmg=data[18];
                oastc=data[19];
                if(opp.equals("Mud Monster"))
                {
                    if(!playerDodges)
                    {
                        stun=true;
                    }
                }
                else
                    oppbuffround=true;
            }
            else if (oppopt==-1)
            {
                oadmg=0;
                oastc=0;
            }
            if(buffround&&data[50]>1)
            {
                admg=(int)Math.round(admg*1.25);
                oadmg=(int)Math.round(oadmg*0.75);
                ++data[50];
            }
            else if(buffround)
                ++data[50];
            if(oppbuffround&&data[51]>1)
            {
                if(opp.equals("Goblin"))
                {
                    admg=(int)Math.round(admg*0.75);
                    oadmg=(int)Math.round(oadmg*0.75);
                    ++data[51];
                }
                else
                {
                    admg=(int)Math.round(admg*0.75);
                    oadmg=(int)Math.round(oadmg*1.25);
                    ++data[51];
                }
            }
            else if(oppbuffround)
                ++data[51];
            if(opppowerup)
                oadmg*=2;
            if(torf[10])
            {
                admg=(int)Math.round(admg*1.05);
                System.out.println(SEP+"[Impera effect on, 5% damage bonus for "+chrct+"!]");
            }
            else if(torf[11])
            {
                admg=(int)Math.round(admg*1.1);
                System.out.println(SEP+"[Impera effect on, 10% damage bonus for "+chrct+"!]");
            }
            else if(torf[12])
            {
                admg=(int)Math.round(admg*1.15);
                System.out.println(SEP+"[Impera effect on, 15% damage bonus for "+chrct+"!]");
            }
            else if(torf[13])
            {
                admg=(int)Math.round(admg*1.2);
                System.out.println(SEP+"[Impera effect on, 20% damage bonus for "+chrct+"!]");
            }
            if(torf[14])
            {
                oadmg=(int)Math.round(oadmg*0.95);
                System.out.println(SEP+"[Aetherion effect on, 5% less damage taken for "+chrct+"!]");            
            }
            else if(torf[15])
            {
                oadmg=(int)Math.round(oadmg*0.9);
                System.out.println(SEP+"[Aetherion effect on, 10% less damage taken for "+chrct+"!]");   
            }
            else if(torf[16])
            {
                oadmg=(int)Math.round(oadmg*0.85);
                System.out.println(SEP+"[Aetherion effect on, 15% less damage taken for "+chrct+"!]");   
            }
            else if(torf[17])
            {
                oadmg=(int)Math.round(oadmg*0.8);
                System.out.println(SEP+"[Aetherion effect on, 20% less damage taken for "+chrct+"!]");   
            }
            // both shield
            if(instakill)
            {
                if(oppopt==2)
                {
                    data[1]-=stamina(astc);
                    if(Choice.equals("1"))
                    {
                        if(opponentDodges)
                        {
                            instakill=false;
                            System.out.println(SEP+chrct+" spent "+stamina(astc)+" stamina, and used "+aopt+".\nHowever, "+opp+" successfully dodged the attack, avoiding getting annihilated by the unforgivable curse...");
                        }
                        else if(!opponentDodges)
                        {
                            data[10]=0;
                            System.out.println(SEP+chrct+" spent "+stamina(astc)+" stamina, and used "+aopt+".\n"+opp+"'s attempt to dodge the attack failed...\n"+SEP+"... SUBTLE FORESHADOWING...\n"+SEP+"WOW, WHAT A MOVE!\n"+chrct+" used "+aopt+", and THE UNFORGIVEABLE CURSE DOES NOT DISAPPOINT!!!\n IT INSTANTLY ERASED "+opp+"'S EXISTENCE!");
                        }
                    }
                    if(Choice.equals("2"))
                    {
                        if(opponentDodges)
                        {
                            instakill=false;
                            System.out.println(SEP+chrct+" spent "+stamina(astc)+" stamina, and used "+aopt+".\nHowever, "+opp+" narrowly dodged the strike, escaping the full force of the legendary One Punch...");                        
                        }
                        else if(!opponentDodges)
                        {
                            data[10]=0;
                            System.out.println(SEP+chrct+" spent "+stamina(astc)+" stamina, and used "+aopt+".\n"+opp+" couldn't evade...\n"+SEP+"The air freezes.\nAbsolute silence.\nONE PUNCH.\n"+chrct+" unleashed a perfectly focused strike, obliterating all of "+opp+"'s remaining strength!");
                        }
                    }
                }
                else
                {
                    if(oppopt==0)
                    {
                        data[1]-=stamina(astc);
                        data[10]=0;
                        if(Choice.equals("1"))
                            System.out.println(SEP+chrct+" spent "+stamina(astc)+" stamina, and used "+aopt+".\n"+opp+" attempted to shield the attack, but... it was no use...\n"+SEP+"... SUBTLE FORESHADOWING...\n"+SEP+"WOW, WHAT A MOVE!\n"+chrct+" used "+aopt+", and THE UNFORGIVEABLE CURSE DOES NOT DISAPPOINT!!!\n IT INSTANTLY ERASED "+opp+"'S EXISTENCE!");
                        else if(Choice.equals("2"))
                            System.out.println(SEP+chrct+" spent "+stamina(astc)+" stamina, and used "+aopt+".\n"+opp+" attempted to shield the punch, but... it was no use...\n"+SEP+"The air freezes.\nAbsolute silence.\nONE PUNCH.\n"+chrct+" unleashed a perfectly focused strike, obliterating all of "+opp+"'s remaining strength!");
                    }
                    else if((opp.equals("Goblin")||opp.equals("Clanka"))&&oppopt==5)
                    {
                        data[1]-=stamina(astc);
                        data[0]-=0;
                        data[11]-=stamina(oastc);
                        data[10]=0;
                        if(Choice.equals("1"))
                            System.out.println(SEP+chrct+" spent "+stamina(astc)+" stamina, and used "+aopt+".\n"+opp+" spent "+stamina(oastc)+" stamina, and used "+oaopt+", attempting to evolve, but it was no use...\n"+SEP+"... SUBTLE FORESHADOWING...\nWOW, WHAT A MOVE!\n"+chrct+" used "+aopt+", and THE UNFORGIVEABLE CURSE DOES NOT DISAPPOINT!!!\nIT INSTANTLY ERASED "+opp+"'S EXISTENCE!");
                        else if(Choice.equals("2"))
                            System.out.println(SEP+chrct+" spent "+stamina(astc)+" stamina, and used "+aopt+".\n"+opp+" spent "+stamina(oastc)+" stamina, and used "+oaopt+", attempting to evolve, but it was no use...\n"+SEP+"The air freezes.\nAbsolute silence.\nONE PUNCH.\n"+chrct+" unleashed a perfectly focused strike, obliterating all of "+opp+"'s remaining strength!");;
                    }
                    else if(oppopt==-1)
                    {
                        data[1]-=stamina(astc);
                        data[10]=0;
                        if(Choice.equals("1"))
                            System.out.println(SEP+"HEARTLESS! "+chrct+" spent "+stamina(astc)+" stamina, and used "+aopt+" while "+opp+" is still incompetent!\n"+SEP+"... SUBTLE FORESHADOWING...\nWOW, WHAT A MOVE!\n"+chrct+" used "+aopt+", and THE UNFORGIVEABLE CURSE DOES NOT DISAPPOINT!!!\nIT INSTANTLY ERASED "+opp+"'S EXISTENCE!");
                        else if(Choice.equals("2"))
                            System.out.println(SEP+chrct+" spent "+stamina(astc)+" stamina, and used "+aopt+" while "+opp+" is still incompetent!\n"+SEP+"The air freezes.\nAbsolute silence.\nONE PUNCH.\n"+chrct+" unleashed a perfectly focused strike, obliterating all of "+opp+"'s remaining strength!");;
                    }
                    else
                    {
                        data[1]-=stamina(astc);
                        data[0]-=damage(false, oadmg);
                        data[11]-=stamina(oastc);
                        data[10]=0;
                        if(Choice.equals("1"))
                            System.out.println(SEP+chrct+" spent "+stamina(astc)+" stamina, and used "+aopt+".\n"+opp+" spent "+stamina(oastc)+" stamina, and used "+oaopt+", and dealt "+damage(false, oadmg)+" damage.\n"+SEP+"... SUBTLE FORESHADOWING...\nWOW, WHAT A MOVE!\n"+chrct+" used "+aopt+", and THE UNFORGIVEABLE CURSE DOES NOT DISAPPOINT!!!\nIT INSTANTLY ERASED "+opp+"'S EXISTENCE!");
                        else if(Choice.equals("2"))
                            System.out.println(SEP+chrct+" spent "+stamina(astc)+" stamina, and used "+aopt+".\n"+opp+" spent "+stamina(oastc)+" stamina, and used "+oaopt+", and dealt "+damage(false, oadmg)+" damage.\n"+SEP+"The air freezes.\nAbsolute silence.\nONE PUNCH.\n"+chrct+" unleashed a perfectly focused strike, obliterating all of "+opp+"'s remaining strength!");;
                    }   
                }
            }
            else if(!instakill)
            {
                if(!stunRound&&!oppstunround)
                {
                    if(oppopt==4&&opp.equals("Mud Monster")&&!opt.equals("2"))
                    {
                        data[10]-=damage(false, admg);
                        data[1]-=stamina(astc);
                        data[0]-=damage(false, oadmg);
                        data[11]-=stamina(oastc);
                        data[10]-=(int)Math.round(0.25*oadmg);
                        if(!opt.equals("0"))
                        {
                            if(Choice.equals("3")&&opt.equals("5"))
                            {
                                System.out.println(SEP+chrct+" spent "+stamina(astc)+" stamina, and used "+aopt+".");
                                System.out.println(opp+" spent "+stamina(oastc)+" stamina, and used "+oaopt+", and dealt "+damage(false, oadmg)+" damage.\nHowever, as "+opp+" self destructed, it took in 25% of the damage it dealt.");
                            }
                            else
                            {
                                System.out.println(SEP+chrct+" spent "+stamina(astc)+" stamina, and used "+aopt+", and dealt "+damage(false, admg)+" damage.");
                                System.out.println(opp+" spent "+stamina(oastc)+" stamina, and used "+oaopt+", and dealt "+damage(false, oadmg)+" damage.\nHowever, as "+opp+" self destructed, it took in 25% of the damage it dealt.");
                            }
                        }
                        else
                            System.out.println(SEP+chrct+" shielded, but "+opp+" used "+oaopt+" and guard broke, dealing "+damage(false, oadmg)+" damage.\nHowever, as "+opp+" self destructed, it took in 25% of the damage it dealt.");
                    }
                    else
                    {
                        if(Choice.equals("3")&&opt.equals("5")&&(opp.equals("Goblin")||opp.equals("Clanka"))&&oppopt==5)
                        {
                            data[1]-=stamina(astc);
                            data[11]-=stamina(oastc);
                            System.out.println(SEP+chrct+" spent "+stamina(astc)+" stamina, and used "+aopt+".\n"+opp+" spent "+stamina(oastc)+" stamina, and used "+oaopt+".");
                        }
                        else if(Choice.equals("3")&&opt.equals("5")&&oppopt!=0&&oppopt!=2)
                        {
                            data[10]-=damage(false, admg);
                            data[1]-=stamina(astc);
                            data[0]-=damage(false, oadmg);
                            data[11]-=stamina(oastc);
                            System.out.println(SEP+chrct+" spent "+stamina(astc)+" stamina, and used "+aopt+".\n"+opp+" spent "+stamina(oastc)+" stamina, and used "+oaopt+", and dealt "+damage(false, oadmg)+" damage.");
                        }
                        else if(oppopt==0&&Choice.equals("3")&&opt.equals("5"))// opponent shields, player uses unc super
                        {
                            data[10]-=damage(true, admg); // opponent shield halves incoming damage
                            data[1]-=stamina(astc); // player spends stamina
                            System.out.println(chrct+" spent "+stamina(astc)+" stamina, and used "+aopt+".");
                        }
                        else if(oppopt==2&&Choice.equals("3")&&opt.equals("5"))// opponent dodges, player uses unc super
                        {
                            data[1]-=stamina(astc); // player spends stamina
                            data[10]-=damage(false, admg);
                            System.out.println(SEP+chrct+" spent "+stamina(astc)+" stamina, and used "+aopt+".\n"+opp+" attempted to dodge.");
                        }
                        else if((opp.equals("Goblin")||opp.equals("Clanka"))&&oppopt==5&&!opt.equals("0")&&!opt.equals("2"))
                        {
                            data[10]-=damage(false, admg);
                            data[1]-=stamina(astc);
                            data[0]-=damage(false, oadmg);
                            data[11]-=stamina(oastc);
                            System.out.println(SEP+opp+" spent "+stamina(oastc)+" stamina, and used "+oaopt+".\n"+chrct+" spent "+stamina(astc)+" stamina, and used "+aopt+"");
                        }
                        else if(opt.equals("0")&&(opp.equals("Goblin")||opp.equals("Clanka"))&&oppopt==5)// opponent shields, player uses unc super
                        {
                            data[0]-=damage(true, oadmg); // opponent shield halves incoming damage
                            data[11]-=stamina(oastc); // player spends stamina
                            System.out.println(opp+" spent "+stamina(oastc)+" stamina, and used "+oaopt+".");
                        }
                        else if(opt.equals("2")&&(opp.equals("Goblin")||opp.equals("Clanka"))&&oppopt==5)// opponent dodges, player uses unc super
                        {
                            data[11]-=stamina(oastc); // player spends stamina
                            data[0]-=damage(false, oadmg);
                            System.out.println(SEP+opp+" spent "+stamina(oastc)+" stamina, and used "+oaopt+".\n"+chrct+" attempted to dodge.");
                        }
                        else if(opt.equals("0")&&oppopt==0)//both shield
                            System.out.println(SEP+"You both shielded yourselves, no damage is done.");
                        else if(opt.equals("0")&&oppopt!=0&&oppopt!=2)// player shields, opponent attacks or uses ability/super
                        {
                            data[0]-=damage(true, oadmg); // player's shield halves incoming damage
                            data[11]-=stamina(oastc); // opponent spends stamina to attack
                            System.out.println(opp+" spent "+stamina(oastc)+" stamina, and used "+oaopt+", and dealt "+damage(true, oadmg)+" damage.");
                        }
                        else if(oppopt==0&&!opt.equals("0") && !opt.equals("2"))// opponent shields, player attacks or uses ability/super
                        {
                            data[10]-=damage(true, admg); // opponent shield halves incoming damage
                            data[1]-=stamina(astc); // player spends stamina
                            System.out.println(chrct+" spent "+stamina(astc)+" stamina, and used "+aopt+", and dealt "+damage(true, admg)+" damage.");
                        }
                        else if(opt.equals("2") && oppopt==2)// both tried to dodge
                        {
                            System.out.println(SEP+"You both attempted to dodge, no damage is done.");
                        }
                        else if(opt.equals("2")&&oppopt!=0&&oppopt!=2)// player dodges, opponent used a non-dodge non-shield move
                        {
                            data[11]-=stamina(oastc); // opponent spends stamina
                            if(playerDodges) // successful player dodge -> no damage to player
                            {
                                System.out.println(opp+" spent "+stamina(oastc)+" stamina, and used "+oaopt+".\nHowever, "+chrct+" successfully dodged the attack, avoiding all impact.");
                            }
                            else // failed dodge -> player takes normal (non-shielded) damage
                            {
                                if(opp.equals("Mud Monster")&&oppopt==4)
                                {
                                    data[0]-=damage(false, oadmg);
                                    data[11]-=stamina(oastc);
                                    data[10]-=(int)Math.round(0.25*oadmg);
                                    System.out.println(SEP+chrct+"'s dodge attempt failed, and received "+damage(false, oadmg)+" damage.\nHowever, as "+opp+" self destructed, it took in 25% of the damage it dealt.");           
                                }
                                else
                                {
                                    data[0]-=damage(false, oadmg);
                                    System.out.println(SEP+opp+" spent "+stamina(oastc)+" stamina, and used "+oaopt+".\n"+chrct+"'s attempt to dodge the attack failed, and received "+damage(false, oadmg)+" damage.");
                                }  
                            }
                        }
                        else if(oppopt==2&&!opt.equals("0")&&!opt.equals("2"))// opponent dodges, player used a non-dodge non-shield move
                        {
                            data[1]-=stamina(astc); // player spends stamina
                            if(opponentDodges)
                            {
                                System.out.println(SEP+chrct+" spent "+stamina(astc)+" stamina, and used "+aopt+".\nHowever, "+opp+" successfully dodged the attack, avoiding all impact.");
                            }
                            else
                            {
                                data[10]-=damage(false, admg);
                                System.out.println(SEP+chrct+" spent "+stamina(astc)+" stamina, and used "+aopt+".\n"+opp+"'s attempt to dodge the attack failed, and received "+damage(false, admg)+" damage.");
                            }
                        }
                        else if(opt.equals("2") && oppopt==0)// player attempted dodge but opponent shielded (no damage)
                            System.out.println(SEP+opp+" shielded, "+chrct+" attempted to dodge, no damage is done.");
                        else if(oppopt==2 && opt.equals("0"))// opponent attempted dodge but player shielded (no damage)
                            System.out.println(SEP+chrct+" shielded, "+opp+" attempted to dodge, no damage is done.");
                        else//general case: both sides used attacking moves (or one attacked and the other used ability/super)
                        {
                            // apply both sides damage normally, and stamina cost
                            data[10]-=damage(false, admg);
                            data[1]-=stamina(astc);
                            data[0]-=damage(false, oadmg);
                            data[11]-=stamina(oastc);
                            System.out.println(SEP+chrct+" spent "+stamina(astc)+" stamina, and used "+aopt+", and dealt "+damage(false, admg)+" damage.");
                            System.out.println(opp+" spent "+stamina(oastc)+" stamina, and used "+oaopt+", and dealt "+damage(false, oadmg)+" damage.");
                        }
                    }
                    if (stun&&!playerDodges)
                    {
                        if(opp.equals("Goblin"))
                            System.out.println("OH NO! Goblin just 'bought' your all of your intellect! You are unable to perform anything in the next round...");
                        else if(opp.equals("Mud Monster"))
                        {
                            if(oppopt==4)
                                System.out.println("OH NO! The aftermath of Mud Monster's self destruction shook the ground and gave you a concussion! You are stunned and unable to perform anything in the next round...");
                            else if(oppopt==5)
                                System.out.println("OH NO! The aftermath of Mud Monster's compressed you into 2D temporarily and gave you a concussion! You are stunned and unable to perform anything in the next round...");
                        }
                        else
                            System.out.println("OH NO! Clanka stunned you with "+oaopt+". You are unable to perform anything in the next round...");
                    }
                    else if(stun&&playerDodges)
                    {
                        stun=false;
                        stunRound=false;
                    }
                    if (oppstun&&!opponentDodges)
                    {
                        if(Choice.equals("2"))
                            System.out.println("WOW! "+chrct+" just snatched "+opp+"'s soul with "+aopt+"! It will be unable to perform anything in the next round...");
                    }
                    else if(oppstun&&opponentDodges)
                    {
                        oppstun=false;
                        oppstunround=false;
                    }
                }
                else if(stunRound&&oppstunround)
                {
                    System.out.println(SEP+"Both "+chrct+" and "+opp+" are not able to perform anything this round, press any key to confirm.");
                    kb.nextLine();
                    stunRound=false;
                    oppstunround=false;
                }
                else if(stunRound&&!oppstunround)
                {
                    System.out.println("You are unable to perform any actions this round, press any key to confirm.");
                    kb.nextLine();
                    if(oppopt==2&&opt.equals("-1"))
                        System.out.println(SEP+chrct+" is unable to perform anything.\nLuckily, "+opp+" didn't seize the chance and chose to dodge.\nNo damage is done.");
                    else if(oppopt==0&&opt.equals("-1"))
                        System.out.println(SEP+chrct+" is unable to perform anything.\nLuckily, "+opp+" didn't seize the chance and chose to shield.\nNo damage is done.");
                    else
                    {
                        if(opp.equals("Mud Monster")&&oppopt==4)
                        {
                            data[0]-=damage(false, oadmg);
                            data[11]-=stamina(oastc);
                            data[10]-=(int)Math.round(0.25*oadmg);
                            System.out.println(SEP+chrct+"received "+damage(false, oadmg)+" damage.\nHowever, as "+opp+" self destructed, it took in 25% of the damage it dealt.");           
                        }
                        else
                        {    
                            data[0]-=damage(false, oadmg);
                            data[11]-=stamina(oastc);
                            System.out.println(SEP+opp+" spent "+stamina(oastc)+" stamina, and used "+oaopt+", doing "+damage(false, oadmg)+" damage to "+chrct+".");
                        }
                    }
                    if (stun)
                    {
                        if(opp.equals("Goblin"))
                            System.out.println("OH NO! Goblin just 'bought' your all of your intellect! You are unable to perform anything in the next round...");
                        else if(opp.equals("Mud Monster"))
                        {
                            if(oppopt==4)
                                System.out.println("OH NO! The aftermath of Mud Monster's self destruction shook the ground and gave you a concussion! You are stunned and unable to perform anything in the next round...");
                            else if(oppopt==5)
                                System.out.println("OH NO! The aftermath of Mud Monster's compressed you into 2D temporarily and gave you a concussion! You are stunned and unable to perform anything in the next round...");
                        }
                        else
                            System.out.println("OH NO! Clanka stunned you with "+oaopt+". You are unable to perform anything in the next round...");
                    }
                    else
                        stunRound=false;
                }
                else if(oppstunround&&!stunRound)
                {
                    System.out.println(opp+" is unable to perform any actions this round.");
                    if(opt.equals("2")&&oppopt==-1)
                        System.out.println(SEP+opp+" is unable to perform anything.\nLuckily, "+chrct+" didn't seize the chance and chose to dodge.\nNo damage is done.");
                    else if(opt.equals("0")&&oppopt==-1)
                        System.out.println(SEP+opp+" is unable to perform anything.\nLuckily, "+chrct+" didn't seize the chance and chose to shield.\nNo damage is done.");
                    else
                    {  
                        data[10]-=damage(false,admg);
                        data[1]-=stamina(astc);
                        System.out.println(SEP+chrct+" spent "+stamina(astc)+" stamina, and used "+aopt+", doing "+damage(false,admg)+" damage to "+opp+".");
                    }
                    if (oppstun)
                    {
                        if(Choice.equals("2"))
                            System.out.println("WOW! "+chrct+" just snatched "+opp+"'s soul with "+aopt+"! It will be unable to perform anything in the next round...");
                    }
                    else
                        oppstunround=false;
                }
                if(stun)
                    stunRound=true;
                stun=false;
                if(oppstun)
                    oppstunround=true;
                oppstun=false;
            }
            if(data[0]<=0&&data[10]<=0)//draw scenario, player chooses whether to continue fighting in the same life, restart or return
            {
                System.out.println(SEP+"Oops, you guys did equally well, you eliminated each other at the same time, draw...");
                if (names[52].equals("1")){//ez mode
                    data[60]+=10;
                    System.out.println(SEP+"You are rewarded with 10 sheckles.");
                }
                else if(names[52].equals("2")){//medium
                    data[60]+=15;
                    System.out.println(SEP+"You are rewarded with 15 sheckles.");
                }
                else{//hard
                    data[60]+=20;
                    System.out.println(SEP+"You are rewarded with 20 sheckles.");
                }
                System.out.println(SEP+"Press 0 if you wish to continue fighting.\nPress 1 if you wish to restart a new round of endless mode.\nPress 2 if you wish to return to home menu.");   
                String gameChoice = kb.nextLine();
                while(!gameChoice.equals("0")&&!gameChoice.equals("1")&&!gameChoice.equals("2"))
                {
                    if(torf[1])
                        System.out.println("Invalid entry...\nPress 2 if you wish to re-try the fight.\nPress 2 if you wish to return to home menu.");  
                    else if(torf[2])
                        System.out.println("Invalid entry.\nPress 0 if you wish to continue fighting.\nPress 1 if you wish to restart a new round of endless mode.\nPress 2 if you wish to return to home menu.");   
                    gameChoice = kb.nextLine();
                }
                data[22]=Integer.parseInt(gameChoice);
                if(data[21] > data[20])
                    data[20] = data[21];
                break;
            }
            else if(data[0]<=0)//player got fried... either restart or return to home menu
            {
                System.out.println(SEP+"Bad news "+chrct+", "+opp+" seems to be stronger at this point, you are defeated... Better luck next time!");
                if (names[52].equals("1"))//ez mode
                    System.out.println(SEP+"You are not rewarded with anything.");
                else if(names[52].equals("2")){//medium
                    data[60]+=5;
                    System.out.println(SEP+"You are rewarded with 5 sheckles for your effort.");
                }
                else{//hard
                    data[60]+=10;
                    System.out.println(SEP+"You are rewarded with 10 sheckles for your effort.");
                }
                System.out.println(SEP+"Summary:\nYou managed to defeat " + data[21]+" opponents before your noble sacrifice!\n"+SEP+"Press 1 to start a new round of endless mode.\nPress 2 to return to the homepage.");
                String gameChoice = kb.nextLine();
                while(!gameChoice.equals("0")&&!gameChoice.equals("1"))
                {
                    if(torf[1])
                        System.out.println("Invalid entry...\nPress 1 to re-try the fight.\nPress 2 if you wish to return to home menu.");
                    else if(torf[2])
                        System.out.println("Invalid entry...\nPress 1 to start a new round of endless mode.\nPress 2 to return to the homepage.");
                    gameChoice=kb.nextLine();
                }
                data[22]=Integer.parseInt(gameChoice);
                if(data[21] > data[20])
                    data[20] = data[21];
                break;
            }
            else if(data[10]<=0)//opponent got cooked, player chooses to whether continue fighting in the same life, restart life or quit the game
            {
                System.out.println(SEP+"Great job! "+chrct+", you proved your capability by defeating " + opp + ", this is the " + (data[21] + 1) + " opponent you brought down.");
                if (names[52].equals("1")){//ez
                    data[60]+=30;
                    System.out.println(SEP+"You are rewarded with 30 sheckles.");
                }
                else if(names[52].equals("2")){//medium
                    data[60]+=40;
                    System.out.println(SEP+"You are rewarded with 40 sheckles.");
                }
                else{//hard
                    data[60]+=50;
                    System.out.println(SEP+"You are rewarded with 50 sheckles.");
                }
                System.out.println(SEP+"Press 0 if you wish to continue fighting.\nPress 1 if you wish to restart a new round of endless mode.\nPress 2 if you wish to return to home menu.");
                String gameChoice = kb.nextLine();
                while(!gameChoice.equals("0")&&!gameChoice.equals("1")&&!gameChoice.equals("2"))
                {
                    System.out.println("Invalid choice!\n\nPress 0 if you wish to continue fighting.\nPress 1 if you wish to restart a new round of endless mode.\nPress 2 if you wish to return to home menu.");
                    gameChoice = kb.nextLine();
                }
                data[22]=Integer.parseInt(gameChoice);
                ++data[21];
                if(data[21] > data[20])
                    data[20] = data[21];
                if(Choice.equals("1"))
                    ++data[23];
                else if(Choice.equals("2"))
                    ++data[24];
                else if(Choice.equals("3"))
                    ++data[25];
                break;
            }
        }
        return data;
    }
    public static int damage(boolean shielded,int damage)/*calculates the damage, shielded or not, the damage is already set to the correct value 
    if there's dodge attempt that happens: no damage or normal damage*/
    {   
        if(shielded)
            return (int)Math.round(damage/2.0);
        else
            return damage;
    }
    public static int stamina(int staminaCost)/*calculates the stamina, kind of useless without potions, really just returning what has already been calculated, 
    since the stamina costed, being either normal amount or 0 from shielding or dodging, all which already set to the correct value, 
    but since my code already adapted to this method, it's too late to delet it*/
    {
        return staminaCost;
    }
}
