# Servlet
Adding two numbers
/*servlet.java*/class

package com.example.servletexample;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;

import java.io.PrintWriter;

@WebServlet(urlPatterns = "/AddNumbers")
public class Servletadd extends HttpServlet {
    @Override
    public void doGet(HttpServletRequest req, HttpServletResponse res) throws ServletException, IOException {
//        try (PrintWriter out = res.getWriter()) {
//            int sum;
//            int x, y;
//            String a = req.getParameter("num1");
//            String b = req.getParameter("num2");
        PrintWriter pw = res.getWriter();
           int x = Integer.parseInt(req.getParameter("num1"));
           int y = Integer.parseInt(req.getParameter("num2"));
//            int y = Integer.parseInt(b);
            int sum = x + y;
            pw.println("result is: " + sum);
        }
    }

/*index.jsp*/
<%@ page contentType="text/html; charset=UTF-8" pageEncoding="UTF-8" %>
<!DOCTYPE html>
<html>
<body>
<form action="AddNumbers" >
    <h1>My Jsp project-Adding two numbers</h1><br>
      Enter  first number= :<input type="text"  name="num1"><br/><br/>
      Enter second number= :<input type="text"  name="num2"><br/><br/>
    <input type="submit"><br/>
</form>
</body>
</html>
