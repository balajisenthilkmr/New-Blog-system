// routes/blogRoutes.js
const express = require('express');
const router = express.Router();
const Blog = require('../models/blog');

// Index Route
router.get('/', (req, res) => {
  Blog.find({}, (err, blogs) => {
    if (err) {
      console.error(err);
    } else {
      res.render('index', { blogs });
    }
  });
});

// New Route
router.get('/new', (req, res) => {
  res.render('new');
});

// Create Route
router.post('/', (req, res) => {
  Blog.create(req.body.blog, (err, newBlog) => {
    if (err) {
      console.error(err);
    } else {
      res.redirect('/blogs');
    }
  });
});

// Show Route
router.get('/:id', (req, res) => {
  Blog.findById(req.params.id, (err, foundBlog) => {
    if (err) {
      console.error(err);
    } else {
      res.render('show', { blog: foundBlog });
    }
  });
});

// ... Add edit and delete routes as needed

module.exports = router;
