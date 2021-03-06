# Program Explained
The goal of this program was to use a TRIE data structure to create a simple phonebook that could search for contacts by phone number, first name, and last name. This program represents the beginning of that project implementing the TRIE data structure with the ability to search through first names by Full names or prefixes.

# How to use
To add names into the list we are calling from add them in here
    string contactList[] = {"Seth", "Scott","Sarah","Sammy","Benson","Brandon","Micah","Michael"};

This is how you will call the functions for them to work in the code:

    int main()
    {
        int n = sizeof(contactList)/sizeof(string);
        insertInDirectory(contactList, n);
        string Search;
        cout << "Search: ";
        cin >> Search;
        cout << "Results: " << Search << endl;
        showContacts(Search);
        return 0;
    }

After inserting your contact list you can go about Searching it however you want and the way you will do that is by calling Search in the main function.

The way I called it was by asking for a query in a cout instead of having a set string Search =.

# Data Structure and Search
This program was created using a TRIE data structure due to the fact that there are few data structures that you can add full names and search the letter by letter but also have a value for those full names which can be used as a pointer to another list enabling us to call last names and phone numbers in the future. The TRIE data structure also has a built in search algorithm that you can use to search letter by letter and show the results, prefixes, or full names.

There were failed attempts at using the TRIE data structure with hash tables but in the end the TRIE is more efficient and easier to use.




# doxygen-cmake-github
Demonstrates Doxygen html generation and publishing on GitHub Pages. The Doxygen files for this project can be seen [here](https://semcneil.github.io/doxygen-cmake-github/).

# How to use
1. Point your browser to this repository (https://github.com/semcneil/doxygen-cmake-github)
2. Press the "Use this template" button
3. Give your repository a new name
4. Write a short (one sentence) description of what your project will do
5. Click the Create repository from template button

## VS Code VM Instructions
1. VS Code needs the following extension added:
    1. C/C++ from Microsoft
    2. CMake Tools also from Microsoft
2. Connect to Host in New Window
3. Open a terminal (`ctrl+``)
4. Initialize git if you haven't already using the same email you used on your GitHub account:
    1. `git config --global user.email "you@example.com"`
    2. `git config --global user.name "Your Name"`
5. Navigate to the parent directory for your project
6. Clone your repository using the URL from the GitHub Code button on your repository and on VS Code either clone repository on the Welcome screen or open the Command Palette (ctrl+shift+P), type `git clone` and select `Git: Clone`
    1. Select the parent directory for your project
    2. Open the cloned repository either as prompted or by adding the newly created folder to your workspace by the Welcome tab's Open folder link or File -> Add Folder to Workspace
    3. If you use the command line `git clone` the authentications for pushing to your online repository are not set up
7. If you wait a bit it should ask you which kit you want to use (at the time of this writing I typically use GCC 9.3.0)
8. Allow Intellisense if prompted
9. Edit README.md to reflect your new project
10. Edit the `project` line in the CMakeLists.txt file to have your project's name and version
11. Edit the `add_executable` line in the CMakeLists.txt file to change the name of the executable file to something relevant
12. Change the \@brief, \@details, \@author, and \@date in src/main.cpp
13. To create the PDF on a standard Ubuntu install, the following need to be added: `sudo apt install graphviz texlive-latex-base texlive-latex-recommended texlive-latex-extra`
14. Doxygen also needs installing: `sudo apt install doxygen`
15. In the terminal, change to the `build` directory (should have been automatically generated)
16. Run the following:
    1. `make`
    2. `make docs`
    3. `make pdf`
17. Add the newly named PDF to git staging (`git status` -> `git add docs/yourprojectname.pdf`)
18. Commit all the changes: `git commit -a -m "Initial commit"`
19. Push the changes to GitHub: `git push origin main`
20. Back at your repository on GitHub, refresh the page to show latest commit
21. In the Settings tab, scroll down to GitHub Pages
22. Select "Branch: main" as source and "/docs" as the folder and then press Save
23. Scroll back down to GitHub Pages and click the link to the published site
24. You now have a C++ repository with doxygen output hosted on GitHub Pages
    1. The link usually doesn't work for a while (minutes to hours). This can be worked around by adding `index.html` to the end of the URL. A second commit will also fix it once the commit propagates over to GitHub Pages.
    2. You can see the PDF file generated by Doxygen by adding the name of the PDF to the end of the URL. It will be of the form `projectname.pdf` and can be seen in the `docs` folder.
    3. It can take a few minutes for a new `git push origin main` to propagate over to GitHub Pages
25. Edit README.md to reflect your project usage and point to the Doxygen output for your project
26. Stage the commit (`git add README.md`)
27. Commit (`git commit -a -m "Describe your changes here"`)
28. Push your changes to GitHub as before (`git push origin main`)

## General Usage
During normal development, you will change main.cpp, maybe add more files in the src directory, make them, and run them. To update the documentation on the web do the following at a terminal prompt in your project's `build` directory:
1. `make`
2. `make docs`
3. `make pdf`
Then in your project's root directory do the following:
4. Check the git status: `git status`
5. `git commit -a -m "Describe your changes since last commit"`
    1. The `-a` flag is used to commit all the updated documentation files
    2. VS Code also has git built into it, but the use of branches isn't as easy a workflow as the commandline offers for me (personal opinion).
6. Note that in order for numbered (ordered) lists to work across markdown and Doxygen HTML and PDF outputs they are explicitly numbered vs markdown all being 1. or Doxygen's -#.

# References
1. https://www.doxygen.nl/manual/docblocks.html
2. https://stackoverflow.com/questions/44212101/cmake-how-to-have-add-custom-command-run-after-all-project-files-are-built
3. Very useful overview: https://caiorss.github.io/C-Cpp-Notes/Doxygen-documentation.html
4. https://devblogs.microsoft.com/cppblog/clear-functional-c-documentation-with-sphinx-breathe-doxygen-cmake/
5. https://vicrucann.github.io/tutorials/quick-cmake-doxygen/
6. https://medium.com/practical-coding/c-documentation-with-doxygen-cmake-sphinx-breathe-for-those-of-use-who-are-totally-lost-7d555386fe13
7. https://stackoverflow.com/questions/18590445/cmake-custom-command-to-copy-and-rename
