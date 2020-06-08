import javafx.scene.control.ComboBox;

import javax.print.attribute.standard.PresentationDirection;
import javax.swing.*;
import javax.swing.event.ListSelectionEvent;
import javax.swing.event.ListSelectionListener;
import javax.swing.event.TableModelEvent;
import javax.swing.table.DefaultTableModel;
import javax.swing.table.TableModel;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.awt.event.ContainerEvent;
import java.awt.event.ContainerListener;

class Scratch {


    public static char ca ='F';
    public static  void dialog(){
        JDialog dialog = new JDialog();
        dialog.setSize(400,400);



        JButton button = new JButton("sum");
        JPanel mainPane = new JPanel();
        mainPane.setBounds(50,50,250,250);
        mainPane.add(button);
        mainPane.setBorder(BorderFactory.createTitledBorder("f(x)"));

        dialog.add(mainPane);
        dialog.setVisible(true);
    }
    public static void main(String[] args) {

    JFrame frame = new JFrame("Table");
    frame.setSize(1920,1280);
    frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
    frame.setLayout(null);





    String[] column = new String[9];
    String[][] data =new String[30][10];

    JTextField search = new JTextField();
    JMenuBar menuBar = new JMenuBar();
    JMenu fileM = new JMenu("File");
    JMenu editM = new JMenu("Edit");
    JButton fx = new JButton("F(x)");
    menuBar.add(fileM);
    menuBar.add(editM);
    menuBar.add(fx);
    menuBar.add(search);



    JTextField contChange = new JTextField();
    contChange.setBounds(1100,80,100,20);
    JTextArea conArea = new JTextArea();
    JScrollPane conPane = new JScrollPane(conArea);
    conPane.setBounds(20,550,1200,140);
    conArea.setWrapStyleWord(true);
    conArea.setEditable(false);

    JButton addRow = new JButton("add row");
    addRow.setBounds(1100,20,100,20);
    JButton addColumn = new JButton("add column");
    addColumn.setBounds(1100,50,100,20);



    DefaultTableModel tableModel = new DefaultTableModel(data,column);
    JTable table = new JTable(tableModel);
    JScrollPane scrollPane = new JScrollPane(table);
    scrollPane.setBounds(20,20,1000,480);
    table.setCellSelectionEnabled(true);

    fx.addActionListener(new ActionListener() {
        @Override
        public void actionPerformed(ActionEvent actionEvent) {
            dialog();
        }
    });

    addRow.addActionListener(new ActionListener() {
        @Override
        public void actionPerformed(ActionEvent actionEvent) {
           tableModel.addRow(new String[]{});
           table.setRowSelectionAllowed(true);



        }
    });
    addColumn.addActionListener(new ActionListener() {
        @Override
        public void actionPerformed(ActionEvent actionEvent) {

                if(ca!='Z') {
                    ca += 1;
                    tableModel.addColumn(ca);
                }
        }
    });

    ListSelectionModel listSelectionModel = table.getSelectionModel();
    listSelectionModel.addListSelectionListener(new ListSelectionListener() {
        @Override
        public void valueChanged(ListSelectionEvent listSelectionEvent) {
            conArea.setForeground(Color.black);
            conArea.setText("");
            int n=0;
            for(int i=0; i<table.getRowCount();i++)
                for (int j = 0; j < table.getColumnCount(); j++) {
                    if (table.isCellSelected(i, j)) {
                        conArea.append(table.getColumnName(j) + i + "+");
                        }
                }
        }
    });
        table.editCellAt(table.getSelectedRowCount(),table.getSelectedColumnCount());


    tableModel.fireTableDataChanged();
    frame.add(scrollPane);
    frame.add(addRow);
    frame.add(addColumn);
    frame.add(contChange);
    frame.add(conPane);
    frame.setJMenuBar(menuBar);


    frame.setVisible(true);
}
}
