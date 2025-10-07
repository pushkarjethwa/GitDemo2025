_Welcome to "Communicate using Markdown"! :wave:_

# Git Demo GH-900 Course

![Certification Badge](https://learn.microsoft.com/en-us/media/learn/certification/badges/github-foundations.svg)


### Task List Demo
- [x] List syntax is required
- [x] This item is complete
- [x] This item is not complete


### Login Code 
```
public ActionResult Register()
    {
        //get HttpRequest body object
        var username = HttpContext.Request.Form["username"].ToString();
        var email = HttpContext.Request.Form["email"].ToString();
        var password = HttpContext.Request.Form["password"].ToString();

        //validate user input
        if (string.IsNullOrEmpty(username) || string.IsNullOrEmpty(email) || string.IsNullOrEmpty(password))
        {
            ViewBag.Error = "All fields are required";
            return View();
        }

        //register user to aws rds database table users
        using (var context = new DbContext())
        {
            var user = new User
            {
                Username = username,
                Email = email,
                Password = password
            };
            context.Users.Add(user);
            context.SaveChanges();
        }       
    

        return RedirectToAction("Index");
    }
```
