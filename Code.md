using System;
using System.Web;
using System.Collections.Generic;
using System.Web.UI;
using System.Linq;
using System.Web.UI.WebControls;
using System.Data.SqlClient;
using System.Data;
					
public partial class employees
{
	SqlConnection con = new SqlConnection();
	SqlCommand cmd;
	SqlDataAdapter da; 
	string query;
	protected void employee_details()
	{ 
		con.Open();
		query = "enter employee id";
		cmd = new SqlCommand(query, con);
		SqlDataReader dr = cmd.ExecuteReader();
	
    protected void update_employee(int id, string first_name, string middle_name , string last_name)
	{
         con.Open();
		 cmd.CommandText=" enter employee info (id , first_name, middle_name, last_name) VALUES (@id, @first_name, @middle_mame, @last_name)";
		 cmd.Parameters.AddWithValue("@id");
		 cmd.Parameters.AddWithValue("@first_name");
		 cmd.Parameters.AddWithValue("@middle_name");
		 cmd.Parameters.AddWithValue("@last_name");
		 cmd.ExecuteNonQuery();
		 con.Close();
	}
		
	}
