public double sortListBox(int IsAsc)
        {
		/*
		#########################################################################
		# Loops where originally 'For', but have been redesigned as 'While'. 
	      	# This allows for the loop to be ran in either direction.
		# Approaching it this way cuts back on the amount of required code.
		#
		#
		# IsAsc will either = 0 or 1
		# If button "Asc" is pressed, then sortListBox(1)
		# If button "Desc" is pressed, then sortListBox(0)
		#########################################################################
		*/



            /*#### Input: Get list items ####*/
            string[] listItems = new string[lstOutput.Items.Count];
            int loopStart = 0; int loopStop = 0; int loopStep = 0;
            if (IsAsc == 1) { loopStart = (listItems.Length - 1);   loopStop = -1;                       loopStep = -1; }
            if (IsAsc == 0) { loopStart = 0;                        loopStop = (listItems.Length);       loopStep = 1;  }

            int x = loopStart;
            while(x != loopStop)
            {
                listItems[x] = lstOutput.Items[x].ToString();
                x+=loopStep;
            }

            /*#### Calculate: ####*/
            string msgText = "";
            x = loopStart;
            while(x != loopStop)
            {
                msgText = string.Format("{0}", "[" + x + "] " + listItems[x].ToString()) + "\n" + msgText; 
                        // "\n" also as: System.Environment.NewLine
                x+=loopStep;
            }

            /*#### Output: ####*/
            MessageBox.Show(msgText, "Test Output Message");
            return 0;
        }