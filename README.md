# java
// LOGIN page.......//

import javax.swing.*;
import java.awt.event.*;
import java.awt.*;

public class sw50 extends JFrame
{
	JLabel l1,l2;
	JTextField t1;
	JPasswordField p1;
	JButton b1,b2;
	sw50()
	{
		super("Login");
		setVisible(true);
		setLayout(null);
		setSize(1370,730);
		setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		
		l1 = new JLabel("Enter User Name");
		l1.setForeground(Color.red);
		l1.setFont(new Font("Serif",Font.BOLD,20));
		add(l1);
		l1.setBounds(430,200,200,20);
		
		l2 = new JLabel("Enter Password :");
		l2.setForeground(Color.red);
		
		l2.setFont(new Font("Serif",Font.BOLD,20));
		add(l2);
		l2.setBounds(430,240,200,20);
		
		t1 = new JTextField();
		add(t1);
		t1.setBounds(650,200,200,22);
		
		p1 = new JPasswordField();
		add(p1);
		p1.setBounds(650,240,200,22);
		
		b1 = new JButton("Login");
		add(b1);
		b1.setBounds(540,280,100,22);
		b2 = new JButton("Cancel");
		add(b2);
		b2.setBounds(640,280,100,22);
		b1.addActionListener(new rana());
	}
	class rana implements ActionListener
	{
		public void actionPerformed(ActionEvent e2)
		{
			String u,p;
			int c= 0;
			try
			{
				u = t1.getText();
				p = p1.getText();
				
				if((u.compareTo("Admin"))==0&&(p.compareTo("1234"))==0)
				{
					c++;
				}
				else
				{
					System.out.println("Invalid password");
				}
				if(c>0)
				{
					showData();
					t1.setText("");
					p1.setText("");
				}
			}
			catch(Exception e)
			{
				System.out.println("Invalid User and Password");
			}
		}
		void showData()
		{
			try
			{
				dispose();
				JFrame f1 = new JFrame();
				f1.setVisible(true);
				f1.setSize(1366,736);
				f1.setTitle("Inventory System");
				f1.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
			}
			catch(Exception e)
			{
				System.out.println(e.getMessage());
			}
		}
	}
	public static void main(String mainsh[])
	{
		new sw50();
	}
}
