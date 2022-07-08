# Servlet
Adding two numbers
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
