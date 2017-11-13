using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace wf_tictactoe
{
    public partial class Form1 : Form
    {
        bool turn = true; // when i is treu, its x's turn and false is O's turn
        int turn_count = 0; 

        public Form1()
        {
            InitializeComponent();
        }

        private void aboutToolStripMenuItem_Click(object sender, EventArgs e)
        {
            MessageBox.Show("WRITTEN AND CREATED BY OLA");
        }

        private void exitToolStripMenuItem_Click(object sender, EventArgs e)
        {
            Application.Exit();
        }

        private void button_Click(object sender, EventArgs e)
        {
            turn_count++;
            Button b = (Button)sender;
            if (turn) b.Text = "X"; // this means that if turn then let the button shows "X"

            else b.Text = "O";

            turn =! turn; // this giives the other person a turn.
            b.Enabled = false;

            checkForWinner();
        }

        private void checkForWinner()
        {

            //horizontal check.  This will also have to be called in the button click.  So that once the horoizontal matches, the message comes up
            bool there_is_a_winner = false;
            if ((A1.Text == A2.Text) && (A2.Text == A3.Text)&& (!A1.Enabled))
                there_is_a_winner = true;
           else if ((B1.Text == B2.Text) && (B2.Text == B3.Text) && (!B1.Enabled)) 
            there_is_a_winner = true;
            else if ((C1.Text == C2.Text) && (C2.Text == C3.Text) && (!C1.Enabled)) 
            there_is_a_winner = true;

            //veritcal win
            if ((A1.Text == B1.Text) && (B1.Text ==C1.Text) && (!A1.Enabled))
                there_is_a_winner = true;
            else if ((A2.Text == B2.Text) && (B2.Text == C2.Text) && (!A2.Enabled))
                there_is_a_winner = true;
            else if ((A3.Text == B3.Text) && (B3.Text == C3.Text) && (!A3.Enabled))
                there_is_a_winner = true;

            //diagonal win

            if ((A1.Text == B2.Text) && (B2.Text == C3.Text) && (!A1.Enabled))
                there_is_a_winner = true;
            else if ((A3.Text == B2.Text) && (B2.Text == C1.Text) && (!A3.Enabled))
                there_is_a_winner = true;
            else if ((A3.Text == B3.Text) && (B3.Text == C3.Text) && (!A3.Enabled))
                there_is_a_winner = true;

            //draw scenario
            else { if (turn_count == 9) MessageBox.Show("it was a draw");
                    
            //            }

            //this is what you want to happen if there is a winner or if the winner method is true
            if (there_is_a_winner)
            {
                disableButtons();
                String winner = "";
                if (turn) winner = "O";
                else winner = "X";

                MessageBox.Show(winner + "Wins", "yay");

                                
            }// end if            

        }

        private void disableButtons()
        {
            //looparound all the buttons that are to be disabled.
            try
            {
                foreach (Control c in Controls)
                {
                    Button b = (Button)c;
                    b.Enabled = false;
                    //now go into the methos that checks for a winner and paste in the disable button method/ or call the methos

                }
            }
            catch {
            }
        }
    }
}
