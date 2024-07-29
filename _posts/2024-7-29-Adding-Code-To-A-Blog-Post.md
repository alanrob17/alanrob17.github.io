---
layout: post
title: Testing code blocks
---

This is an example of some code to see how it looks on my blog.

```bash
    internal static void CreateContentPage(List<HtmlFile> htmlFiles)
    {
        var outFile = Environment.CurrentDirectory + "\\Index.html";
        var outStream = File.Create(outFile);
        var sw = new StreamWriter(outStream);

        var title = GetCurrentFolder();
        string header = HtmlPage.CreateHeader(title);
        sw.WriteLine(header);

        foreach (var item in htmlFiles)
        {
            var fullFile = ($"{item.Folder}{item.Name}");

            string content = ProcessFiles.GetContent(fullFile);
            sw.WriteLine(content);
        }

        string footer = HtmlPage.CreateFooter();
        sw.WriteLine(footer);

        // flush and close
        sw.Flush();
        sw.Close();
    }
```
