# name - Abdullah Iqbal
# reg-no - KEG/IT/2021/F/0040

## i have created the Read/View function in this project (foodMs)

## I have created the adminDashboard.form and viewFoods.form ,   If we click the view button in adminDashboard JFrame a Jtable form will be popup with Field names and data. also i have added a SQL Exception it will run if we cannot retrive the data from database
## i have provided an extra code in adminDashboard.form (commented) , it is a way to view food details without creating table seperately
```
private void formWindowOpened(java.awt.event.WindowEvent evt) {                                  
        Connection con = DbConnection.ConnectDB();
        String sql = "SELECT * FROM food";
        try {
            PreparedStatement pst = con.prepareStatement(sql);
            ResultSet rs = pst.executeQuery();

            while (rs.next()) {
                String id = rs.getString("id");
                String name = rs.getString("name");
                String price = rs.getString("price");
                String description = rs.getString("description");

                String tblData[] = {id, name, price, description};

                DefaultTableModel model = (DefaultTableModel) viewTbl.getModel();
                model.addRow(tblData);

            }
        } catch (SQLException ex) {
            JOptionPane.showMessageDialog(this, "Error Retrieving Data: " + ex.getMessage(), "Error", JOptionPane.ERROR_MESSAGE);
        }
    }

```      

  **Group members**

### Rimza - KEG/IT/2021/F/0010 - Delete function (deleteFoods.form)

### Aadhil - KEG/IT/2021/F/0027 - Update function (updateFood.form)

### Aakila - KEG/IT/2021/F/0065 - Insert function (addFoods.form)


