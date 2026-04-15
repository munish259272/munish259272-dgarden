---
{"dg-publish":true,"permalink":"/home/","tags":["gardenEntry"],"dg-note-properties":{"cssclasses":["dashboard"],"banner":"[istockphoto-1442611988-2048x2048.jpg](/img/user/attachments/istockphoto-1442611988-2048x2048.jpg)","banner_y":0.5,"banner_x":0.5,"modified":"2026-04-14T22:54:57+05:30"}}
---



# 🎓**Learning**

## Academic

```button
name Generate Markers and Folder Structure for <span style="font-size: 1.2em; font-weight: bold; color: #3b82f6;">Academic</span>
type chain
templater true
actions [
  {
    "type": "append text",
    "action": "<%* try { const currentFile = app.workspace.getActiveFile(); if (!currentFile || currentFile.path !== 'Home.md') { return; } const basePath = 'Learning/Academic'; const folders = app.vault.getAllLoadedFiles().filter(file => file.children && file.path.startsWith(basePath + '/')).map(folder => folder.path.replace(basePath + '/', '').split('/')[0]).filter((value, index, self) => value && self.indexOf(value) === index); if (!folders.length) { tR += `Error: No subfolders found under ${basePath}`; return; } const content = await app.vault.read(currentFile); const sorted = Array.from(folders).sort(); const markerRegex = new RegExp(`^<!--\\\\s*${sorted[0]}_START\\\\s*-->`, 'm'); if (content.match(markerRegex)) { return; } const comments = sorted.map(folder => `<!-- ${folder}_START -->\\n<!-- ${folder}_END -->`).join('\\n\\n'); tR += comments; } catch (error) { tR += `Error: ${error.message}`; } %>"
  },
  {
    "type": "command",
    "action": "<%* try { const currentNote = 'Home.md'; const basePath = 'Learning/Academic'; const folders = app.vault.getAllLoadedFiles().filter(file => file.children && file.path.startsWith(basePath + '/')).map(folder => ({ path: folder.path, title: folder.path.split('/').pop() })).filter((folder, index, self) => self.findIndex(f => f.path === folder.path) === index && folder.path.split('/').length === basePath.split('/').length + 1); if (!folders.length) { tR += `Error: No subfolders found under ${basePath}`; return; } for (const folder of folders) { const lastFolder = folder.path.split('/').pop(); const startMarker = `<!-- ${lastFolder}_START -->`; const endMarker = `<!-- ${lastFolder}_END -->`; const output = await tp.user.generateFolderStructure(folder.path, '> ', 3); console.log(`Checking ${startMarker} to ${endMarker} in ${currentNote}`); await tp.user.replaceInNote(currentNote, startMarker, endMarker, output); } } catch (error) { tR += `Error: ${error.message}`; } %>"
  }
]
```
<!-- Economics_START -->

> [!multi-column] 
> 
> > [!g-gray]- Economics
> > 
> > > 
> > > 
> > > 
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > |  | [[Learning/Academic/Economics/Economics\|Economics]] |
> > > 
> > > > [!g-white]- KhanAcademy
> > > > 
> > > > 
> > > > > [!g-white]- Finance and Capital Markets
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Finance and Capital Markets | [[Learning/Academic/Economics/KhanAcademy/Finance and Capital Markets/Finance and Capital Markets\|Finance and Capital Markets]] |
> > > > > | Finance Resources and College courses | [[Learning/Academic/Economics/KhanAcademy/Finance and Capital Markets/Finance Resources and College courses/Quantitative Finance MS and PhD\|Quantitative Finance MS and PhD]] |
> > > > > | Unit 1 - Interest and debt | [[Learning/Academic/Economics/KhanAcademy/Finance and Capital Markets/Unit 1 - Interest and debt/Unit 1 - Interest and debt\|Unit 1 - Interest and debt]] |
> > > > > | Unit 10 - Current economics | [[Learning/Academic/Economics/KhanAcademy/Finance and Capital Markets/Unit 10 - Current economics/Unit 10 - Current economics\|Unit 10 - Current economics]] |
> > > > > | Unit 2 - Housing | [[Learning/Academic/Economics/KhanAcademy/Finance and Capital Markets/Unit 2 - Housing/Unit 2 - Housing\|Unit 2 - Housing]] |
> > > > > | Unit 3 - Inflation | [[Learning/Academic/Economics/KhanAcademy/Finance and Capital Markets/Unit 3 - Inflation/Unit 3 - Inflation\|Unit 3 - Inflation]] |
> > > > > | Unit 4 - Taxes | [[Learning/Academic/Economics/KhanAcademy/Finance and Capital Markets/Unit 4 - Taxes/Unit 4 - Taxes\|Unit 4 - Taxes]] |
> > > > > | Unit 5 - Accounting and financial statements | [[Learning/Academic/Economics/KhanAcademy/Finance and Capital Markets/Unit 5 - Accounting and financial statements/Unit 5 - Accounting and financial statements\|Unit 5 - Accounting and financial statements]] |
> > > > > | Unit 6 - Stocks and bonds | [[Learning/Academic/Economics/KhanAcademy/Finance and Capital Markets/Unit 6 - Stocks and bonds/Unit 6 - Stocks and bonds\|Unit 6 - Stocks and bonds]] |
> > > > > | Unit 7 - Investment vehicles, insurance, and retirement | [[Learning/Academic/Economics/KhanAcademy/Finance and Capital Markets/Unit 7 - Investment vehicles, insurance, and retirement/Unit 7 - Investment vehicles, insurance, and retirement\|Unit 7 - Investment vehicles, insurance, and retirement]] |
> > > > > | Unit 8 - Money, banking and central banks | [[Learning/Academic/Economics/KhanAcademy/Finance and Capital Markets/Unit 8 - Money, banking and central banks/Unit 8 - Money, banking and central banks\|Unit 8 - Money, banking and central banks]] |
> > > > > | Unit 9 - Options, swaps, futures, MBSs, CDOs, and other derivatives | [[Learning/Academic/Economics/KhanAcademy/Finance and Capital Markets/Unit 9 - Options, swaps, futures, MBSs, CDOs, and other derivatives/Unit 9 - Options, swaps, futures, MBSs, CDOs, and other derivatives\|Unit 9 - Options, swaps, futures, MBSs, CDOs, and other derivatives]] |
> > > > > 
> > > > > > [!g-white]- Finance Resources and College courses
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Finance Resources and College courses | [[Learning/Academic/Economics/KhanAcademy/Finance and Capital Markets/Finance Resources and College courses/Quantitative Finance MS and PhD\|Quantitative Finance MS and PhD]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 1 - Interest and debt
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 1 - Interest and debt | [[Learning/Academic/Economics/KhanAcademy/Finance and Capital Markets/Unit 1 - Interest and debt/Unit 1 - Interest and debt\|Unit 1 - Interest and debt]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 10 - Current economics
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 10 - Current economics | [[Learning/Academic/Economics/KhanAcademy/Finance and Capital Markets/Unit 10 - Current economics/Unit 10 - Current economics\|Unit 10 - Current economics]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 2 - Housing
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 2 - Housing | [[Learning/Academic/Economics/KhanAcademy/Finance and Capital Markets/Unit 2 - Housing/Unit 2 - Housing\|Unit 2 - Housing]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 3 - Inflation
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 3 - Inflation | [[Learning/Academic/Economics/KhanAcademy/Finance and Capital Markets/Unit 3 - Inflation/Unit 3 - Inflation\|Unit 3 - Inflation]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 4 - Taxes
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 4 - Taxes | [[Learning/Academic/Economics/KhanAcademy/Finance and Capital Markets/Unit 4 - Taxes/Unit 4 - Taxes\|Unit 4 - Taxes]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 5 - Accounting and financial statements
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 5 - Accounting and financial statements | [[Learning/Academic/Economics/KhanAcademy/Finance and Capital Markets/Unit 5 - Accounting and financial statements/Unit 5 - Accounting and financial statements\|Unit 5 - Accounting and financial statements]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 6 - Stocks and bonds
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 6 - Stocks and bonds | [[Learning/Academic/Economics/KhanAcademy/Finance and Capital Markets/Unit 6 - Stocks and bonds/Unit 6 - Stocks and bonds\|Unit 6 - Stocks and bonds]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 7 - Investment vehicles, insurance, and retirement
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 7 - Investment vehicles, insurance, and retirement | [[Learning/Academic/Economics/KhanAcademy/Finance and Capital Markets/Unit 7 - Investment vehicles, insurance, and retirement/Unit 7 - Investment vehicles, insurance, and retirement\|Unit 7 - Investment vehicles, insurance, and retirement]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 8 - Money, banking and central banks
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 8 - Money, banking and central banks | [[Learning/Academic/Economics/KhanAcademy/Finance and Capital Markets/Unit 8 - Money, banking and central banks/Unit 8 - Money, banking and central banks\|Unit 8 - Money, banking and central banks]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 9 - Options, swaps, futures, MBSs, CDOs, and other derivatives
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 9 - Options, swaps, futures, MBSs, CDOs, and other derivatives | [[Learning/Academic/Economics/KhanAcademy/Finance and Capital Markets/Unit 9 - Options, swaps, futures, MBSs, CDOs, and other derivatives/Unit 9 - Options, swaps, futures, MBSs, CDOs, and other derivatives\|Unit 9 - Options, swaps, futures, MBSs, CDOs, and other derivatives]] |
> > > > >
> > > > 
> > >
> 
> > [!g-gray]- Math
> > 
> > > 
> > > 
> > > 
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > |  | [[Learning/Academic/Math/resources\|resources]] |
> > > 
> > > > [!g-white]- KhanAcademy
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | KhanAcademy | [[Learning/Academic/Math/KhanAcademy/KhanAcademy\|KhanAcademy]] |
> > > > | Algebra (all content) | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Algebra (all content) - Formulas and Definitions\|Algebra (all content) - Formulas and Definitions]] |
> > > > | Calculus | [[Learning/Academic/Math/KhanAcademy/Calculus/Calculus 1/Calculus 1 - Formulas and Definitions\|Calculus 1 - Formulas and Definitions]] |
> > > > | High School Geometry | [[Learning/Academic/Math/KhanAcademy/High School Geometry/High School Geometry\|High School Geometry]] |
> > > > | Linear Algebra | [[Learning/Academic/Math/KhanAcademy/Linear Algebra/Important Theorems and formulas\|Important Theorems and formulas]] |
> > > > | Precalculus | [[Learning/Academic/Math/KhanAcademy/Precalculus/Precalculus - Formulas and Definations\|Precalculus - Formulas and Definations]] |
> > > > | Statistics and Probability | [[Learning/Academic/Math/KhanAcademy/Statistics and Probability/ExtraInfo/Bayes Theorem\|Bayes Theorem]] |
> > > > 
> > > > > [!g-white]- Algebra (all content)
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Algebra (all content) | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Algebra (all content) - Formulas and Definitions\|Algebra (all content) - Formulas and Definitions]] |
> > > > > | Unit 1 - Introduction to algebra | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Unit 1 - Introduction to algebra/Unit 1 - Introduction to algebra\|Unit 1 - Introduction to algebra]] |
> > > > > | Unit 10 - Polynomial expressions, equations, & functions | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Unit 10 - Polynomial expressions, equations, & functions/Unit 10 - Polynomial expressions, equations, & functions\|Unit 10 - Polynomial expressions, equations, & functions]] |
> > > > > | Unit 11 - Exponential & logarithmic functions | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Unit 11 - Exponential & logarithmic functions/Unit 11 - Exponential & logarithmic functions\|Unit 11 - Exponential & logarithmic functions]] |
> > > > > | Unit 12 - Radical equations & functions | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Unit 12 - Radical equations & functions/Unit 12 - Radical equations & functions\|Unit 12 - Radical equations & functions]] |
> > > > > | Unit 13 - Rational expressions, equations, & functions | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Unit 13 - Rational expressions, equations, & functions/Unit 13 - Rational expressions, equations, & functions\|Unit 13 - Rational expressions, equations, & functions]] |
> > > > > | Unit 14 - Trigonometric functions | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Unit 14 - Trigonometric functions/1.Introduction to radians - Trigonometric functions 1\|1.Introduction to radians - Trigonometric functions 1]] |
> > > > > | Unit 15 - Algebraic modeling | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Unit 15 - Algebraic modeling/Unit 15 - Algebraic modeling\|Unit 15 - Algebraic modeling]] |
> > > > > | Unit 16 - Complex numbers | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Unit 16 - Complex numbers/Unit 16 - Complex numbers\|Unit 16 - Complex numbers]] |
> > > > > | Unit 17 - Conic sections | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Unit 17 - Conic sections/Unit 17 - Conic sections\|Unit 17 - Conic sections]] |
> > > > > | Unit 18 - Series & induction | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Unit 18 - Series & induction/Unit 18 - Series & induction\|UNIT 18 - Series & induction]] |
> > > > > | Unit 19 - Vectors | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Unit 19 - Vectors/Important Theorems and formulas 1\|Important Theorems and formulas 1]] |
> > > > > | Unit 2 - Solving basic equations & inequalities (one variable, linear) | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Unit 2 - Solving basic equations & inequalities (one variable, linear)/Unit 2 - Solving basic equations & inequalities (one variable, linear)\|Unit 2 - Solving basic equations & inequalities (one variable, linear)]] |
> > > > > | Unit 20 - Matrices | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Unit 20 - Matrices/Important Theorems and formulas 1\|Important Theorems and formulas 1]] |
> > > > > | Unit 3 - Linear equations, functions, & graphs | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Unit 3 - Linear equations, functions, & graphs/Unit 3 - Linear equations, functions, & graphs\|Unit 3 - Linear equations, functions, & graphs]] |
> > > > > | Unit 4 - Sequences | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Unit 4 - Sequences/Unit 4 - Sequences\|UNIT 4 - Sequences]] |
> > > > > | Unit 5 - System of equations | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Unit 5 - System of equations/Unit 5 - System of equations\|Unit 5 - System of equations]] |
> > > > > | Unit 6 - Two-variable inequalities | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Unit 6 - Two-variable inequalities/Unit 6 - Two-variable inequalities\|Unit 6 - Two-variable inequalities]] |
> > > > > | Unit 7 - Functions | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Unit 7 - Functions/Questions and Answers 1\|Questions and Answers 1]] |
> > > > > | Unit 8 - Absolute value equations, functions, & inequalities | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Unit 8 - Absolute value equations, functions, & inequalities/Unit 8 - Absolute value equations, functions, & inequalities\|Unit 8 - Absolute value equations, functions, & inequalities]] |
> > > > > | Unit 9 - Quadratic equations & functions | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Unit 9 - Quadratic equations & functions/Unit 9 - Quadratic equations & functions\|Unit 9 - Quadratic equations & functions]] |
> > > > > 
> > > > > > [!g-white]- Unit 1 - Introduction to algebra
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 1 - Introduction to algebra | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Unit 1 - Introduction to algebra/Unit 1 - Introduction to algebra\|Unit 1 - Introduction to algebra]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 10 - Polynomial expressions, equations, & functions
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 10 - Polynomial expressions, equations, & functions | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Unit 10 - Polynomial expressions, equations, & functions/Unit 10 - Polynomial expressions, equations, & functions\|Unit 10 - Polynomial expressions, equations, & functions]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 11 - Exponential & logarithmic functions
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 11 - Exponential & logarithmic functions | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Unit 11 - Exponential & logarithmic functions/Unit 11 - Exponential & logarithmic functions\|Unit 11 - Exponential & logarithmic functions]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 12 - Radical equations & functions
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 12 - Radical equations & functions | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Unit 12 - Radical equations & functions/Unit 12 - Radical equations & functions\|Unit 12 - Radical equations & functions]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 13 - Rational expressions, equations, & functions
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 13 - Rational expressions, equations, & functions | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Unit 13 - Rational expressions, equations, & functions/Unit 13 - Rational expressions, equations, & functions\|Unit 13 - Rational expressions, equations, & functions]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 14 - Trigonometric functions
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 14 - Trigonometric functions | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Unit 14 - Trigonometric functions/1.Introduction to radians - Trigonometric functions 1\|1.Introduction to radians - Trigonometric functions 1]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 15 - Algebraic modeling
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 15 - Algebraic modeling | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Unit 15 - Algebraic modeling/Unit 15 - Algebraic modeling\|Unit 15 - Algebraic modeling]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 16 - Complex numbers
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 16 - Complex numbers | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Unit 16 - Complex numbers/Unit 16 - Complex numbers\|Unit 16 - Complex numbers]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 17 - Conic sections
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 17 - Conic sections | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Unit 17 - Conic sections/Unit 17 - Conic sections\|Unit 17 - Conic sections]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 18 - Series & induction
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 18 - Series & induction | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Unit 18 - Series & induction/Unit 18 - Series & induction\|UNIT 18 - Series & induction]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 19 - Vectors
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 19 - Vectors | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Unit 19 - Vectors/Important Theorems and formulas 1\|Important Theorems and formulas 1]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 2 - Solving basic equations & inequalities (one variable, linear)
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 2 - Solving basic equations & inequalities (one variable, linear) | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Unit 2 - Solving basic equations & inequalities (one variable, linear)/Unit 2 - Solving basic equations & inequalities (one variable, linear)\|Unit 2 - Solving basic equations & inequalities (one variable, linear)]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 20 - Matrices
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 20 - Matrices | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Unit 20 - Matrices/Important Theorems and formulas 1\|Important Theorems and formulas 1]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 3 - Linear equations, functions, & graphs
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 3 - Linear equations, functions, & graphs | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Unit 3 - Linear equations, functions, & graphs/Unit 3 - Linear equations, functions, & graphs\|Unit 3 - Linear equations, functions, & graphs]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 4 - Sequences
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 4 - Sequences | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Unit 4 - Sequences/Unit 4 - Sequences\|UNIT 4 - Sequences]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 5 - System of equations
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 5 - System of equations | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Unit 5 - System of equations/Unit 5 - System of equations\|Unit 5 - System of equations]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 6 - Two-variable inequalities
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 6 - Two-variable inequalities | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Unit 6 - Two-variable inequalities/Unit 6 - Two-variable inequalities\|Unit 6 - Two-variable inequalities]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 7 - Functions
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 7 - Functions | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Unit 7 - Functions/Questions and Answers 1\|Questions and Answers 1]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 8 - Absolute value equations, functions, & inequalities
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 8 - Absolute value equations, functions, & inequalities | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Unit 8 - Absolute value equations, functions, & inequalities/Unit 8 - Absolute value equations, functions, & inequalities\|Unit 8 - Absolute value equations, functions, & inequalities]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 9 - Quadratic equations & functions
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 9 - Quadratic equations & functions | [[Learning/Academic/Math/KhanAcademy/Algebra (all content)/Unit 9 - Quadratic equations & functions/Unit 9 - Quadratic equations & functions\|Unit 9 - Quadratic equations & functions]] |
> > > > > > 
> > > > 
> > > > > [!g-white]- Calculus
> > > > > 
> > > > > 
> > > > > > [!g-white]- Calculus 1
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Calculus 1 | [[Learning/Academic/Math/KhanAcademy/Calculus/Calculus 1/Calculus 1 - Formulas and Definitions\|Calculus 1 - Formulas and Definitions]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Calculus 2
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Calculus 2 | [[Learning/Academic/Math/KhanAcademy/Calculus/Calculus 2/Calculus 2\|Calculus 2]] |
> > > > > > 
> > > > 
> > > > > [!g-white]- High School Geometry
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | High School Geometry | [[Learning/Academic/Math/KhanAcademy/High School Geometry/High School Geometry\|High School Geometry]] |
> > > > > | Unit 6 - Analytic geometry | [[Learning/Academic/Math/KhanAcademy/High School Geometry/Unit 6 - Analytic geometry/6.1.1 Getting ready for analytic geometry\|6.1.1 Getting ready for analytic geometry]] |
> > > > > 
> > > > > > [!g-white]- Unit 6 - Analytic geometry
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 6 - Analytic geometry | [[Learning/Academic/Math/KhanAcademy/High School Geometry/Unit 6 - Analytic geometry/6.1.1 Getting ready for analytic geometry\|6.1.1 Getting ready for analytic geometry]] |
> > > > > > 
> > > > 
> > > > > [!g-white]- Linear Algebra
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Linear Algebra | [[Learning/Academic/Math/KhanAcademy/Linear Algebra/Important Theorems and formulas\|Important Theorems and formulas]] |
> > > > > | Unit 1 - Vectors and spaces | [[Learning/Academic/Math/KhanAcademy/Linear Algebra/Unit 1 - Vectors and spaces/1.Vectors - Vectors and spaces\|1.Vectors - Vectors and spaces]] |
> > > > > | Unit 2 - Matrix transformations | [[Learning/Academic/Math/KhanAcademy/Linear Algebra/Unit 2 - Matrix transformations/10.Transformations and matrix multiplication - Matrix transformations\|10.Transformations and matrix multiplication - Matrix transformations]] |
> > > > > | Unit 3 - Alternate coordinate systems (bases) | [[Learning/Academic/Math/KhanAcademy/Linear Algebra/Unit 3 - Alternate coordinate systems (bases)/15.Orthogonal complements - Alternate coordinate systems (bases)\|15.Orthogonal complements - Alternate coordinate systems (bases)]] |
> > > > > 
> > > > > > [!g-white]- Extra Resources
> > > > > > 
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 1 - Vectors and spaces
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 1 - Vectors and spaces | [[Learning/Academic/Math/KhanAcademy/Linear Algebra/Unit 1 - Vectors and spaces/1.Vectors - Vectors and spaces\|1.Vectors - Vectors and spaces]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 2 - Matrix transformations
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 2 - Matrix transformations | [[Learning/Academic/Math/KhanAcademy/Linear Algebra/Unit 2 - Matrix transformations/10.Transformations and matrix multiplication - Matrix transformations\|10.Transformations and matrix multiplication - Matrix transformations]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 3 - Alternate coordinate systems (bases)
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 3 - Alternate coordinate systems (bases) | [[Learning/Academic/Math/KhanAcademy/Linear Algebra/Unit 3 - Alternate coordinate systems (bases)/15.Orthogonal complements - Alternate coordinate systems (bases)\|15.Orthogonal complements - Alternate coordinate systems (bases)]] |
> > > > > > 
> > > > 
> > > > > [!g-white]- Precalculus
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Precalculus | [[Learning/Academic/Math/KhanAcademy/Precalculus/Precalculus - Formulas and Definations\|Precalculus - Formulas and Definations]] |
> > > > > 
> > > > > > [!g-white]- Unit 2 - Trigonometry
> > > > > > 
> > > > > > 
> > > > 
> > > > > [!g-white]- Statistics and Probability
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Statistics and Probability | [[Learning/Academic/Math/KhanAcademy/Statistics and Probability/Questions and Answers\|Questions and Answers]] |
> > > > > | ExtraInfo | [[Learning/Academic/Math/KhanAcademy/Statistics and Probability/ExtraInfo/Bayes Theorem\|Bayes Theorem]] |
> > > > > | Unit 1 - Analyzing categorical data | [[Learning/Academic/Math/KhanAcademy/Statistics and Probability/Unit 1 - Analyzing categorical data/Unit 1 - Analyzing categorical data\|Unit 1 - Analyzing categorical data]] |
> > > > > | Unit 10 - Sampling distributions | [[Learning/Academic/Math/KhanAcademy/Statistics and Probability/Unit 10 - Sampling distributions/Unit 10 - Sampling distributions\|Unit 10 - Sampling distributions]] |
> > > > > | Unit 11 - Confidence intervals | [[Learning/Academic/Math/KhanAcademy/Statistics and Probability/Unit 11 - Confidence intervals/Unit 11 - Confidence intervals\|Unit 11 - Confidence intervals]] |
> > > > > | Unit 12 - Significance tests (hypothesis testing) | [[Learning/Academic/Math/KhanAcademy/Statistics and Probability/Unit 12 - Significance tests (hypothesis testing)/Unit 12 - Significance tests (hypothesis testing)\|Unit 12 - Significance tests (hypothesis testing)]] |
> > > > > | Unit 13 - Two-sample inference for the difference between groups | [[Learning/Academic/Math/KhanAcademy/Statistics and Probability/Unit 13 - Two-sample inference for the difference between groups/Unit 13 - Two-sample inference for the difference between groups\|Unit 13 - Two-sample inference for the difference between groups]] |
> > > > > | Unit 14 - Inference for categorical data (chi-square tests) | [[Learning/Academic/Math/KhanAcademy/Statistics and Probability/Unit 14 - Inference for categorical data (chi-square tests)/Unit 14 - Inference for categorical data (chi-square tests)\|Unit 14 - Inference for categorical data (chi-square tests)]] |
> > > > > | Unit 15 - Advanced regression (inference and transforming) | [[Learning/Academic/Math/KhanAcademy/Statistics and Probability/Unit 15 - Advanced regression (inference and transforming)/Unit 15 - Advanced regression (inference and transforming)\|Unit 15 - Advanced regression (inference and transforming)]] |
> > > > > | Unit 16 - Analysis of variance (ANOVA) | [[Learning/Academic/Math/KhanAcademy/Statistics and Probability/Unit 16 - Analysis of variance (ANOVA)/Unit 16 - Analysis of variance (ANOVA)\|Unit 16 - Analysis of variance (ANOVA)]] |
> > > > > | Unit 2 - Displaying and comparing quantitative data | [[Learning/Academic/Math/KhanAcademy/Statistics and Probability/Unit 2 - Displaying and comparing quantitative data/Unit 2 - Displaying and comparing quantitative data\|Unit 2 - Displaying and comparing quantitative data]] |
> > > > > | Unit 3 - Summarizing quantitative data | [[Learning/Academic/Math/KhanAcademy/Statistics and Probability/Unit 3 - Summarizing quantitative data/Unit 3 - Summarizing quantitative data\|Unit 3 - Summarizing quantitative data]] |
> > > > > | Unit 4 - Modeling data distributions | [[Learning/Academic/Math/KhanAcademy/Statistics and Probability/Unit 4 - Modeling data distributions/Unit 4 - Modeling data distributions\|Unit 4 - Modeling data distributions]] |
> > > > > | Unit 5 - Exploring bivariate numerical data | [[Learning/Academic/Math/KhanAcademy/Statistics and Probability/Unit 5 - Exploring bivariate numerical data/Unit 5 - Exploring bivariate numerical data\|Unit 5 - Exploring bivariate numerical data]] |
> > > > > | Unit 6 - Study design | [[Learning/Academic/Math/KhanAcademy/Statistics and Probability/Unit 6 - Study design/Unit 6 - Study design\|Unit 6 - Study design]] |
> > > > > | Unit 7 - Probability | [[Learning/Academic/Math/KhanAcademy/Statistics and Probability/Unit 7 - Probability/Unit 7 - Probability\|Unit 7 - Probability]] |
> > > > > | Unit 8 - Counting, permutations, and combinations | [[Learning/Academic/Math/KhanAcademy/Statistics and Probability/Unit 8 - Counting, permutations, and combinations/Unit 8 - Counting, permutations, and combinations\|Unit 8 - Counting, permutations, and combinations]] |
> > > > > | Unit 9 - Random variables | [[Learning/Academic/Math/KhanAcademy/Statistics and Probability/Unit 9 - Random variables/Unit 9 - Random variables\|Unit 9 - Random variables]] |
> > > > > 
> > > > > > [!g-white]- ExtraInfo
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | ExtraInfo | [[Learning/Academic/Math/KhanAcademy/Statistics and Probability/ExtraInfo/Bayes Theorem\|Bayes Theorem]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 1 - Analyzing categorical data
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 1 - Analyzing categorical data | [[Learning/Academic/Math/KhanAcademy/Statistics and Probability/Unit 1 - Analyzing categorical data/Unit 1 - Analyzing categorical data\|Unit 1 - Analyzing categorical data]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 10 - Sampling distributions
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 10 - Sampling distributions | [[Learning/Academic/Math/KhanAcademy/Statistics and Probability/Unit 10 - Sampling distributions/Unit 10 - Sampling distributions\|Unit 10 - Sampling distributions]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 11 - Confidence intervals
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 11 - Confidence intervals | [[Learning/Academic/Math/KhanAcademy/Statistics and Probability/Unit 11 - Confidence intervals/Unit 11 - Confidence intervals\|Unit 11 - Confidence intervals]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 12 - Significance tests (hypothesis testing)
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 12 - Significance tests (hypothesis testing) | [[Learning/Academic/Math/KhanAcademy/Statistics and Probability/Unit 12 - Significance tests (hypothesis testing)/Unit 12 - Significance tests (hypothesis testing)\|Unit 12 - Significance tests (hypothesis testing)]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 13 - Two-sample inference for the difference between groups
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 13 - Two-sample inference for the difference between groups | [[Learning/Academic/Math/KhanAcademy/Statistics and Probability/Unit 13 - Two-sample inference for the difference between groups/Unit 13 - Two-sample inference for the difference between groups\|Unit 13 - Two-sample inference for the difference between groups]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 14 - Inference for categorical data (chi-square tests)
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 14 - Inference for categorical data (chi-square tests) | [[Learning/Academic/Math/KhanAcademy/Statistics and Probability/Unit 14 - Inference for categorical data (chi-square tests)/Unit 14 - Inference for categorical data (chi-square tests)\|Unit 14 - Inference for categorical data (chi-square tests)]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 15 - Advanced regression (inference and transforming)
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 15 - Advanced regression (inference and transforming) | [[Learning/Academic/Math/KhanAcademy/Statistics and Probability/Unit 15 - Advanced regression (inference and transforming)/Unit 15 - Advanced regression (inference and transforming)\|Unit 15 - Advanced regression (inference and transforming)]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 16 - Analysis of variance (ANOVA)
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 16 - Analysis of variance (ANOVA) | [[Learning/Academic/Math/KhanAcademy/Statistics and Probability/Unit 16 - Analysis of variance (ANOVA)/Unit 16 - Analysis of variance (ANOVA)\|Unit 16 - Analysis of variance (ANOVA)]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 2 - Displaying and comparing quantitative data
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 2 - Displaying and comparing quantitative data | [[Learning/Academic/Math/KhanAcademy/Statistics and Probability/Unit 2 - Displaying and comparing quantitative data/Unit 2 - Displaying and comparing quantitative data\|Unit 2 - Displaying and comparing quantitative data]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 3 - Summarizing quantitative data
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 3 - Summarizing quantitative data | [[Learning/Academic/Math/KhanAcademy/Statistics and Probability/Unit 3 - Summarizing quantitative data/Unit 3 - Summarizing quantitative data\|Unit 3 - Summarizing quantitative data]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 4 - Modeling data distributions
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 4 - Modeling data distributions | [[Learning/Academic/Math/KhanAcademy/Statistics and Probability/Unit 4 - Modeling data distributions/Unit 4 - Modeling data distributions\|Unit 4 - Modeling data distributions]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 5 - Exploring bivariate numerical data
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 5 - Exploring bivariate numerical data | [[Learning/Academic/Math/KhanAcademy/Statistics and Probability/Unit 5 - Exploring bivariate numerical data/Unit 5 - Exploring bivariate numerical data\|Unit 5 - Exploring bivariate numerical data]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 6 - Study design
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 6 - Study design | [[Learning/Academic/Math/KhanAcademy/Statistics and Probability/Unit 6 - Study design/Unit 6 - Study design\|Unit 6 - Study design]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 7 - Probability
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 7 - Probability | [[Learning/Academic/Math/KhanAcademy/Statistics and Probability/Unit 7 - Probability/Unit 7 - Probability\|Unit 7 - Probability]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 8 - Counting, permutations, and combinations
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 8 - Counting, permutations, and combinations | [[Learning/Academic/Math/KhanAcademy/Statistics and Probability/Unit 8 - Counting, permutations, and combinations/Unit 8 - Counting, permutations, and combinations\|Unit 8 - Counting, permutations, and combinations]] |
> > > > > > 
> > > > > 
> > > > > > [!g-white]- Unit 9 - Random variables
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Unit 9 - Random variables | [[Learning/Academic/Math/KhanAcademy/Statistics and Probability/Unit 9 - Random variables/Unit 9 - Random variables\|Unit 9 - Random variables]] |
> > > > > > 
> > > 
> > > > [!g-white]- Udemy
> > > > 
> > > > 
> > > > > [!g-white]- Statistics
> > > > > 
> > > > > 
> > > > > > [!g-white]- Mathematical Statistics for Data Science
> > > > > > 
> > > > > > | Folder | First File Link |
> > > > > > | --- | --- |
> > > > > > | Mathematical Statistics for Data Science | [[Learning/Academic/Math/Udemy/Statistics/Mathematical Statistics for Data Science/Mathematical Statistics for Data Science\|Mathematical Statistics for Data Science]] |
> > > > > >

<!-- Economics_END -->

<!-- Math_START -->

<!-- Math_END -->

## Basic Electronics, Design Thinking, Networking, Prompts


```button
name Generate Markers and Folder Structure for <span style="font-size: 1.2em; font-weight: bold; color: #3b82f6;">Basic Electronics, Design Thinking, Networking, Prompts</span>
type chain
templater true
actions [
  {
    "type": "append text",
    "action": "<%* try { const currentFile = app.workspace.getActiveFile(); if (!currentFile || currentFile.path !== 'Home.md') { return; } const folders = ['Basic Electronics', 'Design Thinking', 'Networking', 'Prompts']; const content = await app.vault.read(currentFile); const sorted = folders.sort(); const markerRegex = new RegExp(`^<!--\\\\s*${sorted[0]}_START\\\\s*-->`, 'm'); if (content.match(markerRegex)) { return; } const comments = sorted.map(folder => `<!-- ${folder}_START -->\\n<!-- ${folder}_END -->`).join('\\n\\n'); tR += comments; } catch (error) { tR += `Error: ${error.message}`; } %>"
  },
  {
    "type": "command",
    "action": "<%* try { const currentNote = tp.file.path(true); const basePath = 'Learning'; const folders = [{ path: `${basePath}/Basic Electronics`, title: 'Electronics Courses' }, { path: `${basePath}/Design Thinking`, title: 'Programming Courses' }, { path: `${basePath}/Networking`, title: 'Networking Courses' }, { path: `${basePath}/Prompts`, title: 'AI Prompts' }]; for (const folder of folders) { const lastFolder = folder.path.split('/').pop(); const startMarker = `<!-- ${lastFolder}_START -->`; const endMarker = `<!-- ${lastFolder}_END -->`; const output = await tp.user.generateFolderStructure(folder.path, '> ', 3); console.log(`Checking ${startMarker} to ${endMarker} in ${currentNote}`); await tp.user.replaceInNote(currentNote, startMarker, endMarker, output); } } catch (error) { tR += `Error: ${error.message}`; } %>"
  }
]
```


> [!multi-column]
> 
> > [!g-gray]- Basic Electronics
> > 
> > 
> > | Folder | First File Link |
> > | --- | --- |
> > |  | [[Learning/Basic Electronics/Resources\|Resources]] |
> >
> 
> > [!g-gray]- Design Thinking
> > 
> > 
> > 
> > | Folder | First File Link |
> > | --- | --- |
> > |  | [[Learning/Design Thinking/Questions\|Questions]] |
> >
> 
> 
> > [!g-gray]- Networking
> > 
> > 
> > 
> > | Folder | First File Link |
> > | --- | --- |
> > |  | [[Learning/Networking/Networking\|Networking]] |
> > 
> > > [!g-white]- Networking_IpFundamentals
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | Networking_IpFundamentals | [[Learning/Networking/Networking_IpFundamentals/1-Part 1 Lesson 1 - Identify Network Devices in a Topology\|1-Part 1 Lesson 1 - Identify Network Devices in a Topology]] |
> > >
> 
> > [!g-gray]- Prompts
> > 
> > 
> > 
> > | Folder | First File Link |
> > | --- | --- |
> > |  | [[Learning/Prompts/Assignment 1\|Assignment 1]] |
> 

<!-- Basic Electronics_START -->

<!-- Basic Electronics_END -->

<!-- Design Thinking_START -->
 

<!-- Design Thinking_END -->

<!-- Networking_START -->

<!-- Networking_END -->

<!-- Prompts_START -->

<!-- Prompts_END -->


## Programming


```button
name Generate Markers and Folder Structure for <span style="font-size: 1.2em; font-weight: bold; color: #3b82f6;">Programming</span>
type chain
templater true
actions [
  {
    "type": "append text",
    "action": "<%* try { const currentFile = app.workspace.getActiveFile(); if (!currentFile || currentFile.path !== 'Home.md') { return; } const basePath = 'Learning/Programming'; const folders = app.vault.getAllLoadedFiles().filter(file => file.children && file.path.startsWith(basePath + '/')).map(folder => folder.path.replace(basePath + '/', '').split('/')[0]).filter((value, index, self) => value && self.indexOf(value) === index); if (!folders.length) { tR += `Error: No subfolders found under ${basePath}`; return; } const content = await app.vault.read(currentFile); const sorted = Array.from(folders).sort(); const markerRegex = new RegExp(`^<!--\\\\s*${sorted[0]}_START\\\\s*-->`, 'm'); if (content.match(markerRegex)) { return; } const comments = sorted.map(folder => `<!-- ${folder}_START -->\\n<!-- ${folder}_END -->`).join('\\n\\n'); tR += comments; } catch (error) { tR += `Error: ${error.message}`; } %>"
  },
  {
    "type": "command",
    "action": "<%* try { const currentNote = 'Home.md'; const basePath = 'Learning/Programming'; const folders = app.vault.getAllLoadedFiles().filter(file => file.children && file.path.startsWith(basePath + '/')).map(folder => ({ path: folder.path, title: folder.path.split('/').pop() })).filter((folder, index, self) => self.findIndex(f => f.path === folder.path) === index && folder.path.split('/').length === basePath.split('/').length + 1); if (!folders.length) { tR += `Error: No subfolders found under ${basePath}`; return; } for (const folder of folders) { const lastFolder = folder.path.split('/').pop(); const startMarker = `<!-- ${lastFolder}_START -->`; const endMarker = `<!-- ${lastFolder}_END -->`; const output = await tp.user.generateFolderStructure(folder.path, '> ', 3); console.log(`Checking ${startMarker} to ${endMarker} in ${currentNote}`); await tp.user.replaceInNote(currentNote, startMarker, endMarker, output); } } catch (error) { tR += `Error: ${error.message}`; } %>"
  }
]
```
<!-- Android_START -->
> [!g-gray] Android
> 
> > [!multi-column]
> > 
> > 
> > No files
> > 
> > > [!g-white]- Flutter
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | Flutter | [[Learning/Programming/Android/Flutter/Important General info\|Important General info]] |
> > > | Flutter & Dart - The Complete Guide 2025 Edition | [[Learning/Programming/Android/Flutter/Flutter & Dart - The Complete Guide 2025 Edition/Section 1 - Introduction/1. Welcome To This Course!\|1. Welcome To This Course!]] |
> > > 
> > > > [!g-white]- Flutter & Dart - The Complete Guide 2025 Edition
> > > > 
> > > > 
> > > > > [!g-white]- Section 1 - Introduction
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 1 - Introduction | [[Learning/Programming/Android/Flutter/Flutter & Dart - The Complete Guide 2025 Edition/Section 1 - Introduction/1. Welcome To This Course!\|1. Welcome To This Course!]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 10 - Animations - MEALS APP
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 10 - Animations - MEALS APP | [[Learning/Programming/Android/Flutter/Flutter & Dart - The Complete Guide 2025 Edition/Section 10 - Animations - MEALS APP/191. Module Introduction\|191. Module Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 11 - Handling User Input and Working with Forms - SHOPPING LIST APP
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 11 - Handling User Input and Working with Forms - SHOPPING LIST APP | [[Learning/Programming/Android/Flutter/Flutter & Dart - The Complete Guide 2025 Edition/Section 11 - Handling User Input and Working with Forms - SHOPPING LIST APP/207. Module Introduction\|207. Module Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 12 - Connecting a Backend and Sending HTTP Requests - SHOPPING LIST APP
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 12 - Connecting a Backend and Sending HTTP Requests - SHOPPING LIST APP | [[Learning/Programming/Android/Flutter/Flutter & Dart - The Complete Guide 2025 Edition/Section 12 - Connecting a Backend and Sending HTTP Requests - SHOPPING LIST APP/221. Module Introduction\|221. Module Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 13 - Using Native Device Features - e.g., Camera - FAVORITE PLACES APP
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 13 - Using Native Device Features - e.g., Camera - FAVORITE PLACES APP | [[Learning/Programming/Android/Flutter/Flutter & Dart - The Complete Guide 2025 Edition/Section 13 - Using Native Device Features - e.g., Camera - FAVORITE PLACES APP/237. Module Introduction\|237. Module Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 14 - Push Notifications and More - Building a Chat App with Flutter and Firebase
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 14 - Push Notifications and More - Building a Chat App with Flutter and Firebase | [[Learning/Programming/Android/Flutter/Flutter & Dart - The Complete Guide 2025 Edition/Section 14 - Push Notifications and More - Building a Chat App with Flutter and Firebase/271. Module Introduction\|271. Module Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 15 - About The Course Update
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 15 - About The Course Update | [[Learning/Programming/Android/Flutter/Flutter & Dart - The Complete Guide 2025 Edition/Section 15 - About The Course Update/305. About the Course Update and How To Proceed\|305. About the Course Update and How To Proceed]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 16 - Next Steps and Roundup
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 16 - Next Steps and Roundup | [[Learning/Programming/Android/Flutter/Flutter & Dart - The Complete Guide 2025 Edition/Section 16 - Next Steps and Roundup/307. Publishing iOS and Android Apps\|307. Publishing iOS and Android Apps]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 2 - Flutter and Dart Basics I - Getting a Solid Foundation - ROLL DICE APP
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 2 - Flutter and Dart Basics I - Getting a Solid Foundation - ROLL DICE APP | [[Learning/Programming/Android/Flutter/Flutter & Dart - The Complete Guide 2025 Edition/Section 2 - Flutter and Dart Basics I - Getting a Solid Foundation - ROLL DICE APP/14. Module Introduction\|14. Module Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 3 - Flutter and Dart Basics II - Fundamentals Deep Dive - QUIZ APP
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 3 - Flutter and Dart Basics II - Fundamentals Deep Dive - QUIZ APP | [[Learning/Programming/Android/Flutter/Flutter & Dart - The Complete Guide 2025 Edition/Section 3 - Flutter and Dart Basics II - Fundamentals Deep Dive - QUIZ APP/53. Module Introduction\|53. Module Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 4 - Debugging Flutter Apps
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 4 - Debugging Flutter Apps | [[Learning/Programming/Android/Flutter/Flutter & Dart - The Complete Guide 2025 Edition/Section 4 - Debugging Flutter Apps/92. Module Introduction\|92. Module Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 5 - Adding Interactivity, More Widgets and Theming - EXPENSE TRACKER
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 5 - Adding Interactivity, More Widgets and Theming - EXPENSE TRACKER | [[Learning/Programming/Android/Flutter/Flutter & Dart - The Complete Guide 2025 Edition/Section 5 - Adding Interactivity, More Widgets and Theming - EXPENSE TRACKER/100. Adding an Expense Data Model with a Unique ID and Exploring Initializer Lists\|100. Adding an Expense Data Model with a Unique ID and Exploring Initializer Lists]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 6 - Building Responsive and Adaptive User Interfaces - EXPENSE TRACKER APP
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 6 - Building Responsive and Adaptive User Interfaces - EXPENSE TRACKER APP | [[Learning/Programming/Android/Flutter/Flutter & Dart - The Complete Guide 2025 Edition/Section 6 - Building Responsive and Adaptive User Interfaces - EXPENSE TRACKER APP/135. Module Introduction\|135. Module Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 7 - Flutter and Dart Internals - TODO APP
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 7 - Flutter and Dart Internals - TODO APP | [[Learning/Programming/Android/Flutter/Flutter & Dart - The Complete Guide 2025 Edition/Section 7 - Flutter and Dart Internals - TODO APP/145. Module Introduction\|145. Module Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 8 - Building Multi-Screen Apps and Navigating Between Screens - MEALS APP
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 8 - Building Multi-Screen Apps and Navigating Between Screens - MEALS APP | [[Learning/Programming/Android/Flutter/Flutter & Dart - The Complete Guide 2025 Edition/Section 8 - Building Multi-Screen Apps and Navigating Between Screens - MEALS APP/154. Module Introduction\|154. Module Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 9 - Managing State - MEALS APP
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 9 - Managing State - MEALS APP | [[Learning/Programming/Android/Flutter/Flutter & Dart - The Complete Guide 2025 Edition/Section 9 - Managing State - MEALS APP/177. Module Introduction\|177. Module Introduction]] |
> > > > >
<!-- Android_END -->

<!-- C&T_START -->
> [!g-gray] C&T
> 
> > [!multi-column]
> > 
> > 
> > 
> > | Folder | First File Link |
> > | --- | --- |
> > |  | [[Learning/Programming/C&T/Fastest way to become a Data Engineer in 2024 - 100 Days Of Data Engineering\|Fastest way to become a Data Engineer in 2024 - 100 Days Of Data Engineering]] |
> > 
> > > [!g-white]- 365datascience.com
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | 365datascience.com | [[Learning/Programming/C&T/365datascience.com/365datascience.com\|365datascience.com]] |
> > > 
> > 
> > > [!g-white]- Database tutorial
> > > 
> > > 
> > > > [!g-white]- MongoDB
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | MongoDB | [[Learning/Programming/C&T/Database tutorial/MongoDB/Prompt Used\|Prompt Used]] |
> > > > | Section 1 - Introduction | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 1 - Introduction/1. Introduction\|1. Introduction]] |
> > > > | Section 10 - Working with Indexes | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 10 - Working with Indexes/126. Module Introduction\|126. Module Introduction]] |
> > > > | Section 11 - Working with Geospatial Data | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 11 - Working with Geospatial Data/150. Module Introduction\|150. Module Introduction]] |
> > > > | Section 12 - Understanding the Aggregation Framework | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 12 - Understanding the Aggregation Framework/160. Module Introduction\|160. Module Introduction]] |
> > > > | Section 13 - Working with Numeric Data | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 13 - Working with Numeric Data/186. Module Introduction\|186. Module Introduction]] |
> > > > | Section 14 - MongoDB & Security | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 14 - MongoDB & Security/197. Module Introduction\|197. Module Introduction]] |
> > > > | Section 15 - Performance, Fault Tolerancy & Deployment | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 15 - Performance, Fault Tolerancy & Deployment/208. Module Introduction\|208. Module Introduction]] |
> > > > | Section 16 - Transactions | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 16 - Transactions/219. Module Introduction\|219. Module Introduction]] |
> > > > | Section 17 - From Shell to Driver | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 17 - From Shell to Driver/224. Module Introduction\|224. Module Introduction]] |
> > > > | Section 18 - Introducing Stitch | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 18 - Introducing Stitch/243. Module Introduction\|243. Module Introduction]] |
> > > > | Section 19 - Roundup | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 19 - Roundup/264. Course Roundup\|264. Course Roundup]] |
> > > > | Section 2 - Understanding the Basics & CRUD Operations | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 2 - Understanding the Basics & CRUD Operations/15. Module Introduction\|15. Module Introduction]] |
> > > > | Section 3 - Schemas & Relations How to Structure Documents | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 3 - Schemas & Relations How to Structure Documents/34. Resetting Your Database\|34. Resetting Your Database]] |
> > > > | Section 4 - Exploring The Shell & The Server | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 4 - Exploring The Shell & The Server/58. Module Introduction\|58. Module Introduction]] |
> > > > | Section 5 - Using the MongoDB Compass to Explore Data Visually | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 5 - Using the MongoDB Compass to Explore Data Visually/66. Module Introduction\|66. Module Introduction]] |
> > > > | Section 6 - Diving Into Create Operations | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 6 - Diving Into Create Operations/69. Module Introduction\|69. Module Introduction]] |
> > > > | Section 7 - Read Operations - A Closer Look | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 7 - Read Operations - A Closer Look/100. Sorting Cursor Results\|100. Sorting Cursor Results]] |
> > > > | Section 8 - Update Operations | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 8 - Update Operations/106. Module Introduction\|106. Module Introduction]] |
> > > > | Section 9 - Understanding Delete Operations | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 9 - Understanding Delete Operations/122. Module Introduction\|122. Module Introduction]] |
> > > > 
> > > > > [!g-white]- Section 1 - Introduction
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 1 - Introduction | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 1 - Introduction/1. Introduction\|1. Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 10 - Working with Indexes
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 10 - Working with Indexes | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 10 - Working with Indexes/126. Module Introduction\|126. Module Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 11 - Working with Geospatial Data
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 11 - Working with Geospatial Data | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 11 - Working with Geospatial Data/150. Module Introduction\|150. Module Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 12 - Understanding the Aggregation Framework
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 12 - Understanding the Aggregation Framework | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 12 - Understanding the Aggregation Framework/160. Module Introduction\|160. Module Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 13 - Working with Numeric Data
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 13 - Working with Numeric Data | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 13 - Working with Numeric Data/186. Module Introduction\|186. Module Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 14 - MongoDB & Security
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 14 - MongoDB & Security | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 14 - MongoDB & Security/197. Module Introduction\|197. Module Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 15 - Performance, Fault Tolerancy & Deployment
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 15 - Performance, Fault Tolerancy & Deployment | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 15 - Performance, Fault Tolerancy & Deployment/208. Module Introduction\|208. Module Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 16 - Transactions
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 16 - Transactions | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 16 - Transactions/219. Module Introduction\|219. Module Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 17 - From Shell to Driver
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 17 - From Shell to Driver | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 17 - From Shell to Driver/224. Module Introduction\|224. Module Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 18 - Introducing Stitch
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 18 - Introducing Stitch | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 18 - Introducing Stitch/243. Module Introduction\|243. Module Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 19 - Roundup
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 19 - Roundup | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 19 - Roundup/264. Course Roundup\|264. Course Roundup]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 2 - Understanding the Basics & CRUD Operations
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 2 - Understanding the Basics & CRUD Operations | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 2 - Understanding the Basics & CRUD Operations/15. Module Introduction\|15. Module Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 3 - Schemas & Relations How to Structure Documents
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 3 - Schemas & Relations How to Structure Documents | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 3 - Schemas & Relations How to Structure Documents/34. Resetting Your Database\|34. Resetting Your Database]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 4 - Exploring The Shell & The Server
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 4 - Exploring The Shell & The Server | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 4 - Exploring The Shell & The Server/58. Module Introduction\|58. Module Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 5 - Using the MongoDB Compass to Explore Data Visually
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 5 - Using the MongoDB Compass to Explore Data Visually | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 5 - Using the MongoDB Compass to Explore Data Visually/66. Module Introduction\|66. Module Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 6 - Diving Into Create Operations
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 6 - Diving Into Create Operations | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 6 - Diving Into Create Operations/69. Module Introduction\|69. Module Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 7 - Read Operations - A Closer Look
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 7 - Read Operations - A Closer Look | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 7 - Read Operations - A Closer Look/100. Sorting Cursor Results\|100. Sorting Cursor Results]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 8 - Update Operations
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 8 - Update Operations | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 8 - Update Operations/106. Module Introduction\|106. Module Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 9 - Understanding Delete Operations
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 9 - Understanding Delete Operations | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 9 - Understanding Delete Operations/122. Module Introduction\|122. Module Introduction]] |
> > > > > 
> > > 
> > > > [!g-white]- PostgreSQL
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | PostgreSQL | [[Learning/Programming/C&T/Database tutorial/PostgreSQL/01 - Introduction\|01 - Introduction]] |
> > > > 
> > 
> > > [!g-white]- Domain Knowledge
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | Domain Knowledge | [[Learning/Programming/C&T/Domain Knowledge/Resources\|Resources]] |
> > > 
> > 
> > > [!g-white]- HowItsDone
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | HowItsDone | [[Learning/Programming/C&T/HowItsDone/Latex\|Latex]] |
> > > 
> > 
> > > [!g-white]- Learnbay
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | Learnbay | [[Learning/Programming/C&T/Learnbay/contact and support info\|contact and support info]] |
> > > | DL & NLP | [[Learning/Programming/C&T/Learnbay/DL & NLP/1. Class 1 , Oct 5, 2024\|1. Class 1 , Oct 5, 2024]] |
> > > | git and github | [[Learning/Programming/C&T/Learnbay/git and github/26. Class 49 , Mar 2, 2024, Sat ( Git and GitHub)\|26. Class 49 , Mar 2, 2024, Sat ( Git and GitHub)]] |
> > > | OOPS | [[Learning/Programming/C&T/Learnbay/OOPS/25. Class 47 , Feb 24, 2024, Sat ( OOPS)\|25. Class 47 , Feb 24, 2024, Sat ( OOPS)]] |
> > > | python | [[Learning/Programming/C&T/Learnbay/python/1. Class 1 , August 27, 2023 ( cohort session )\|1. Class 1 , August 27, 2023 ( cohort session )]] |
> > > | SQL & Mongo DB | [[Learning/Programming/C&T/Learnbay/SQL & Mongo DB/1.SQL & Mongo DB By Sagar- 6th July 2024\|1.SQL & Mongo DB By Sagar- 6th July 2024]] |
> > > | Statistics & Machine Learning | [[Learning/Programming/C&T/Learnbay/Statistics & Machine Learning/0. Stats By Dhruv/10.Stats & ML By Dhruv- 14 Mar 2024\|10.Stats & ML By Dhruv- 14 Mar 2024]] |
> > > 
> > > > [!g-white]- DL & NLP
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | DL & NLP | [[Learning/Programming/C&T/Learnbay/DL & NLP/1. Class 1 , Oct 5, 2024\|1. Class 1 , Oct 5, 2024]] |
> > > > 
> > > 
> > > > [!g-white]- git and github
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | git and github | [[Learning/Programming/C&T/Learnbay/git and github/26. Class 49 , Mar 2, 2024, Sat ( Git and GitHub)\|26. Class 49 , Mar 2, 2024, Sat ( Git and GitHub)]] |
> > > > 
> > > 
> > > > [!g-white]- OOPS
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | OOPS | [[Learning/Programming/C&T/Learnbay/OOPS/25. Class 47 , Feb 24, 2024, Sat ( OOPS)\|25. Class 47 , Feb 24, 2024, Sat ( OOPS)]] |
> > > > 
> > > 
> > > > [!g-white]- python
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | python | [[Learning/Programming/C&T/Learnbay/python/1. Class 1 , August 27, 2023 ( cohort session )\|1. Class 1 , August 27, 2023 ( cohort session )]] |
> > > > 
> > > 
> > > > [!g-white]- SQL & Mongo DB
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | SQL & Mongo DB | [[Learning/Programming/C&T/Learnbay/SQL & Mongo DB/1.SQL & Mongo DB By Sagar- 6th July 2024\|1.SQL & Mongo DB By Sagar- 6th July 2024]] |
> > > > 
> > > 
> > > > [!g-white]- Statistics & Machine Learning
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Statistics & Machine Learning | [[Learning/Programming/C&T/Learnbay/Statistics & Machine Learning/20. Class 37 , Jan 20, 2024, Sat ( Statistics)\|20. Class 37 , Jan 20, 2024, Sat ( Statistics)]] |
> > > > | 0. Stats By Dhruv | [[Learning/Programming/C&T/Learnbay/Statistics & Machine Learning/0. Stats By Dhruv/10.Stats & ML By Dhruv- 14 Mar 2024\|10.Stats & ML By Dhruv- 14 Mar 2024]] |
> > > > | practice | [[Learning/Programming/C&T/Learnbay/Statistics & Machine Learning/practice/28. Class 55 , Mar 17, 2024, Sun ( Machine Learning)  practice template\|28. Class 55 , Mar 17, 2024, Sun ( Machine Learning)  practice template]] |
> > > > | Tableau | [[Learning/Programming/C&T/Learnbay/Statistics & Machine Learning/Tableau/37. Class 72 , May 18, 2024, Sat ( Tablaeu)\|37. Class 72 , May 18, 2024, Sat ( Tablaeu)]] |
> > > > | Test run | [[Learning/Programming/C&T/Learnbay/Statistics & Machine Learning/Test run/Test for 28. Class 55 , Mar 17, 2024, Sun\|Test for 28. Class 55 , Mar 17, 2024, Sun]] |
> > > > 
> > > > > [!g-white]- 0. Stats By Dhruv
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | 0. Stats By Dhruv | [[Learning/Programming/C&T/Learnbay/Statistics & Machine Learning/0. Stats By Dhruv/10.Stats & ML By Dhruv- 14 Mar 2024\|10.Stats & ML By Dhruv- 14 Mar 2024]] |
> > > > > 
> > > > 
> > > > > [!g-white]- course files
> > > > > 
> > > > > 
> > > > 
> > > > > [!g-white]- practice
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | practice | [[Learning/Programming/C&T/Learnbay/Statistics & Machine Learning/practice/28. Class 55 , Mar 17, 2024, Sun ( Machine Learning)  practice template\|28. Class 55 , Mar 17, 2024, Sun ( Machine Learning)  practice template]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Tableau
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Tableau | [[Learning/Programming/C&T/Learnbay/Statistics & Machine Learning/Tableau/37. Class 72 , May 18, 2024, Sat ( Tablaeu)\|37. Class 72 , May 18, 2024, Sat ( Tablaeu)]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Test run
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Test run | [[Learning/Programming/C&T/Learnbay/Statistics & Machine Learning/Test run/Test for 28. Class 55 , Mar 17, 2024, Sun\|Test for 28. Class 55 , Mar 17, 2024, Sun]] |
> > > > > 
> > 
> > > [!g-white]- ML&AI
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | ML&AI | [[Learning/Programming/C&T/ML&AI/Interview and Preplacement Preparation\|Interview and Preplacement Preparation]] |
> > > | anaconda setup | [[Learning/Programming/C&T/ML&AI/anaconda setup/Environment name - learnbay\|Environment name - learnbay]] |
> > > | bookvideos | [[Learning/Programming/C&T/ML&AI/bookvideos/Understanding Machine Learning - From Theory to Algorithms/1 VideoNotes - Machine Learning course- Shai Ben-David： Lecture 1\|1 VideoNotes - Machine Learning course- Shai Ben-David： Lecture 1]] |
> > > | certifications that can be done | [[Learning/Programming/C&T/ML&AI/certifications that can be done/Certified Analytics Professional (CAP)\|Certified Analytics Professional (CAP)]] |
> > > | Coursera | [[Learning/Programming/C&T/ML&AI/Coursera/Machine Learning Specialization - Stanford - Deeplearning.AIM MOC/ML topics prompt\|ML topics prompt]] |
> > > | CS50 | [[Learning/Programming/C&T/ML&AI/CS50/CS50's Introduction to Artificial Intelligence with Python/1. CS50AI 2023 - Introduction\|1. CS50AI 2023 - Introduction]] |
> > > | Interview Questions | [[Learning/Programming/C&T/ML&AI/Interview Questions/Interview questions\|Interview questions]] |
> > > | Projects | [[Learning/Programming/C&T/ML&AI/Projects/coursera\|coursera]] |
> > > | Udemy - Time Series Analysis, Forecasting, and Machine Learning | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Book recommendation and Resources\|Book recommendation and Resources]] |
> > > 
> > > > [!g-white]- anaconda setup
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | anaconda setup | [[Learning/Programming/C&T/ML&AI/anaconda setup/Environment name - learnbay\|Environment name - learnbay]] |
> > > > 
> > > 
> > > > [!g-white]- bookvideos
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | bookvideos | [[Learning/Programming/C&T/ML&AI/bookvideos/bookvideos\|bookvideos]] |
> > > > | Understanding Machine Learning - From Theory to Algorithms | [[Learning/Programming/C&T/ML&AI/bookvideos/Understanding Machine Learning - From Theory to Algorithms/1 VideoNotes - Machine Learning course- Shai Ben-David： Lecture 1\|1 VideoNotes - Machine Learning course- Shai Ben-David： Lecture 1]] |
> > > > 
> > > > > [!g-white]- Understanding Machine Learning - From Theory to Algorithms
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Understanding Machine Learning - From Theory to Algorithms | [[Learning/Programming/C&T/ML&AI/bookvideos/Understanding Machine Learning - From Theory to Algorithms/1 VideoNotes - Machine Learning course- Shai Ben-David： Lecture 1\|1 VideoNotes - Machine Learning course- Shai Ben-David： Lecture 1]] |
> > > > > 
> > > 
> > > > [!g-white]- certifications that can be done
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | certifications that can be done | [[Learning/Programming/C&T/ML&AI/certifications that can be done/Certified Analytics Professional (CAP)\|Certified Analytics Professional (CAP)]] |
> > > > 
> > > 
> > > > [!g-white]- Coursera
> > > > 
> > > > 
> > > > > [!g-white]- DLS
> > > > > 
> > > > > 
> > > > 
> > > > > [!g-white]- Machine Learning Specialization - Stanford - Deeplearning.AI
> > > > > 
> > > > > 
> > > > 
> > > > > [!g-white]- Machine Learning Specialization - Stanford - Deeplearning.AIM MOC
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Machine Learning Specialization - Stanford - Deeplearning.AIM MOC | [[Learning/Programming/C&T/ML&AI/Coursera/Machine Learning Specialization - Stanford - Deeplearning.AIM MOC/ML topics prompt\|ML topics prompt]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Maths for ML & DS Specialization
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Maths for ML & DS Specialization | [[Learning/Programming/C&T/ML&AI/Coursera/Maths for ML & DS Specialization/Coursera - Mathematics for Machine Learning and Data Science Specialization - Formulas and Important points\|Coursera - Mathematics for Machine Learning and Data Science Specialization - Formulas and Important points]] |
> > > > > 
> > > 
> > > > [!g-white]- CS50
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | CS50 | [[Learning/Programming/C&T/ML&AI/CS50/CS50\|CS50]] |
> > > > | CS50's Introduction to Artificial Intelligence with Python | [[Learning/Programming/C&T/ML&AI/CS50/CS50's Introduction to Artificial Intelligence with Python/1. CS50AI 2023 - Introduction\|1. CS50AI 2023 - Introduction]] |
> > > > 
> > > > > [!g-white]- CS50's Introduction to Artificial Intelligence with Python
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | CS50's Introduction to Artificial Intelligence with Python | [[Learning/Programming/C&T/ML&AI/CS50/CS50's Introduction to Artificial Intelligence with Python/1. CS50AI 2023 - Introduction\|1. CS50AI 2023 - Introduction]] |
> > > > > 
> > > 
> > > > [!g-white]- Generative AI
> > > > 
> > > > 
> > > > > [!g-white]- linkedin what-is-generative-ai
> > > > > 
> > > > > 
> > > 
> > > > [!g-white]- Interview Questions
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Interview Questions | [[Learning/Programming/C&T/ML&AI/Interview Questions/Interview questions\|Interview questions]] |
> > > > 
> > > 
> > > > [!g-white]- Projects
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Projects | [[Learning/Programming/C&T/ML&AI/Projects/coursera\|coursera]] |
> > > > 
> > > 
> > > > [!g-white]- Udemy - Time Series Analysis, Forecasting, and Machine Learning
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Udemy - Time Series Analysis, Forecasting, and Machine Learning | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Book recommendation and Resources\|Book recommendation and Resources]] |
> > > > | Section 1 - Welcome | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 1 - Welcome/1. Introduction and Outline\|1. Introduction and Outline]] |
> > > > | Section 10 - Deep Learning - Recurrent Neural Networks (RNN) | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 10 - Deep Learning - Recurrent Neural Networks (RNN)/115. RNN Section Introduction\|115. RNN Section Introduction]] |
> > > > | Section 11 - VIP - GARCH | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 11 - VIP - GARCH/127. GARCH Section Introduction\|127. GARCH Section Introduction]] |
> > > > | Section 12 - VIP - AWS Forecast | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 12 - VIP - AWS Forecast/141. AWS Forecast Section Introduction\|141. AWS Forecast Section Introduction]] |
> > > > | Section 13 - VIP - Facebook Prophet | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 13 - VIP - Facebook Prophet/150. Prophet Section Introduction\|150. Prophet Section Introduction]] |
> > > > | Section 14 - Setting Up Your Environment FAQ | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 14 - Setting Up Your Environment FAQ/161. Pre-Installation Check\|161. Pre-Installation Check]] |
> > > > | Section 15 - Extra Help With Python Coding for Beginners FAQ | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 15 - Extra Help With Python Coding for Beginners FAQ/164. How to Code by Yourself (part 1)\|164. How to Code by Yourself (part 1)]] |
> > > > | Section 16 - Effective Learning Strategies for Machine Learning FAQ | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 16 - Effective Learning Strategies for Machine Learning FAQ/170. How to Succeed in this Course (Long Version)\|170. How to Succeed in this Course (Long Version)]] |
> > > > | Section 17 - Appendix FAQ Finale | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 17 - Appendix FAQ Finale/174. What is the Appendix\|174. What is the Appendix]] |
> > > > | Section 2 - Getting Set Up | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 2 - Getting Set Up/3. Where to get the code, notebooks, and data\|3. Where to get the code, notebooks, and data]] |
> > > > | Section 3 - Time Series Basics | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 3 - Time Series Basics/10. Types of Tasks\|10. Types of Tasks]] |
> > > > | Section 4 - Exponential Smoothing and ETS Methods | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 4 - Exponential Smoothing and ETS Methods/21. Exponential Smoothing Section Introduction\|21. Exponential Smoothing Section Introduction]] |
> > > > | Section 5 - ARIMA | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 5 - ARIMA/41. ARIMA Section Introduction\|41. ARIMA Section Introduction]] |
> > > > | Section 6 - Vector Autoregression (VAR, VMA, VARMA) | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 6 - Vector Autoregression (VAR, VMA, VARMA)/61. Vector Autoregression Section Introduction\|61. Vector Autoregression Section Introduction]] |
> > > > | Section 7 - Machine Learning Methods | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 7 - Machine Learning Methods/72. Machine Learning Section Introduction\|72. Machine Learning Section Introduction]] |
> > > > | Section 8 - Deep Learning - Artificial Neural Networks (ANN) | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 8 - Deep Learning - Artificial Neural Networks (ANN)/100. Human Activity Recognition - Feature-Based Model\|100. Human Activity Recognition - Feature-Based Model]] |
> > > > 
> > > > > [!g-white]- Section 1 - Welcome
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 1 - Welcome | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 1 - Welcome/1. Introduction and Outline\|1. Introduction and Outline]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 10 - Deep Learning - Recurrent Neural Networks (RNN)
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 10 - Deep Learning - Recurrent Neural Networks (RNN) | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 10 - Deep Learning - Recurrent Neural Networks (RNN)/115. RNN Section Introduction\|115. RNN Section Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 11 - VIP - GARCH
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 11 - VIP - GARCH | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 11 - VIP - GARCH/127. GARCH Section Introduction\|127. GARCH Section Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 12 - VIP - AWS Forecast
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 12 - VIP - AWS Forecast | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 12 - VIP - AWS Forecast/141. AWS Forecast Section Introduction\|141. AWS Forecast Section Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 13 - VIP - Facebook Prophet
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 13 - VIP - Facebook Prophet | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 13 - VIP - Facebook Prophet/150. Prophet Section Introduction\|150. Prophet Section Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 14 - Setting Up Your Environment FAQ
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 14 - Setting Up Your Environment FAQ | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 14 - Setting Up Your Environment FAQ/161. Pre-Installation Check\|161. Pre-Installation Check]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 15 - Extra Help With Python Coding for Beginners FAQ
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 15 - Extra Help With Python Coding for Beginners FAQ | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 15 - Extra Help With Python Coding for Beginners FAQ/164. How to Code by Yourself (part 1)\|164. How to Code by Yourself (part 1)]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 16 - Effective Learning Strategies for Machine Learning FAQ
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 16 - Effective Learning Strategies for Machine Learning FAQ | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 16 - Effective Learning Strategies for Machine Learning FAQ/170. How to Succeed in this Course (Long Version)\|170. How to Succeed in this Course (Long Version)]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 17 - Appendix FAQ Finale
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 17 - Appendix FAQ Finale | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 17 - Appendix FAQ Finale/174. What is the Appendix\|174. What is the Appendix]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 2 - Getting Set Up
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 2 - Getting Set Up | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 2 - Getting Set Up/3. Where to get the code, notebooks, and data\|3. Where to get the code, notebooks, and data]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 3 - Time Series Basics
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 3 - Time Series Basics | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 3 - Time Series Basics/10. Types of Tasks\|10. Types of Tasks]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 4 - Exponential Smoothing and ETS Methods
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 4 - Exponential Smoothing and ETS Methods | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 4 - Exponential Smoothing and ETS Methods/21. Exponential Smoothing Section Introduction\|21. Exponential Smoothing Section Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 5 - ARIMA
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 5 - ARIMA | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 5 - ARIMA/41. ARIMA Section Introduction\|41. ARIMA Section Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 6 - Vector Autoregression (VAR, VMA, VARMA)
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 6 - Vector Autoregression (VAR, VMA, VARMA) | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 6 - Vector Autoregression (VAR, VMA, VARMA)/61. Vector Autoregression Section Introduction\|61. Vector Autoregression Section Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 7 - Machine Learning Methods
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 7 - Machine Learning Methods | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 7 - Machine Learning Methods/72. Machine Learning Section Introduction\|72. Machine Learning Section Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 8 - Deep Learning - Artificial Neural Networks (ANN)
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 8 - Deep Learning - Artificial Neural Networks (ANN) | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 8 - Deep Learning - Artificial Neural Networks (ANN)/100. Human Activity Recognition - Feature-Based Model\|100. Human Activity Recognition - Feature-Based Model]] |
> > > > > 
> > 
> > > [!g-white]- Trading
> > > 
> > > 
> > > > [!g-white]- QuantInsti
> > > > 
> > > > 
> > > > > [!g-white]- Dashboard - All Tracks
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Dashboard - All Tracks | [[Learning/Programming/C&T/Trading/QuantInsti/Dashboard - All Tracks/Dashboard - All Tracks\|Dashboard - All Tracks]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Webinars
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Webinars | [[Learning/Programming/C&T/Trading/QuantInsti/Webinars/QuantInsti webinar on 19,Dec 7 PM\|QuantInsti webinar on 19,Dec 7 PM]] |
> > > > > 
> > > 
> > > > [!g-white]- resources
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | resources | [[Learning/Programming/C&T/Trading/resources/aaaquants.com\|aaaquants.com]] |
> > > > 
> > > 
> > > > [!g-white]- Trainings
> > > > 
> > > > 
> > > > > [!g-white]- Tradingmarkets - Quantamentals
> > > > > 
> > > > > 
> > > 
> > > > [!g-white]- upstox
> > > > 
> > > > 
> > > > > [!g-white]- developer api
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | developer api | [[Learning/Programming/C&T/Trading/upstox/developer api/Authentication\|Authentication]] |
> > > > > 
> > > > 
> > > > > [!g-white]- mycode
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | mycode | [[Learning/Programming/C&T/Trading/upstox/mycode/progressing\|progressing]] |
> > > > > 
> > > 
> > > > [!g-white]- zerodha varsity
> > > > 
> > > > 
> > > > > [!g-white]- 1. Introduction to Stock Markets
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | 1. Introduction to Stock Markets | [[Learning/Programming/C&T/Trading/zerodha varsity/1. Introduction to Stock Markets/1. The Need to Invest\|1. The Need to Invest]] |
> > > > > 
> > > > 
> > > > > [!g-white]- 2. Technical Analysis
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | 2. Technical Analysis | [[Learning/Programming/C&T/Trading/zerodha varsity/2. Technical Analysis/13. Moving Averages\|13. Moving Averages]] |
> > > > > 
> > 
> > > [!g-white]- web development
> > > 
> > > 
> > > > [!g-white]- css youtube
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | css youtube | [[Learning/Programming/C&T/web development/css youtube/HTML5 and CSS3 - 33 - Width, Max-Width, Min-Width - YouTube\|HTML5 and CSS3 - 33 - Width, Max-Width, Min-Width - YouTube]] |
> > > > 
> > > 
> > > > [!g-white]- Javascript
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Javascript | [[Learning/Programming/C&T/web development/Javascript/async\|async]] |
> > > > 
> > > > > [!g-white]- JavaScript - The Complete Guide 2025
> > > > > 
> > > > > 
> > > > 
> > > > > [!g-white]- JavaScript - The Complete Guide 2025 (Beginner + Advanced)
> > > > > 
> > > > > 
> > > 
> > > > [!g-white]- Kevin Powell
> > > > 
> > > > 
> > > > > [!g-white]- CSS Demystified - Start Writing CSS with Confidence (Module 1-3)
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | CSS Demystified - Start Writing CSS with Confidence (Module 1-3) | [[Learning/Programming/C&T/web development/Kevin Powell/CSS Demystified - Start Writing CSS with Confidence (Module 1-3)/Untitled\|Untitled]] |
> > > > >
<!-- C&T_END -->

<!-- Git and Github_START -->
> [!g-gray] Git and Github
> 
> > [!multi-column]
> > 
> > 
> > No files
> > 
> > > [!g-white]- The Git and Github Bootcamp
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | The Git and Github Bootcamp | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/The Git & Github Bootcamp MOC\|The Git & Github Bootcamp MOC]] |
> > > | section 1 - Course Orientation | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 1 - Course Orientation/1. Welcome To The Course!\|1. Welcome To The Course!]] |
> > > | section 10 - Undoing Changes & Time Traveling | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 10 - Undoing Changes & Time Traveling/81. What Really Matters In This Section\|81. What Really Matters In This Section]] |
> > > | section 11 - Github - The Basics | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 11 - Github - The Basics/100. Touring A Github Repo\|100. Touring A Github Repo]] |
> > > | section 12 - Fetching & Pulling | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 12 - Fetching & Pulling/107. What Really Matters In This Section\|107. What Really Matters In This Section]] |
> > > | section 13 - Github Grab Bag - Odds & Ends | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 13 - Github Grab Bag - Odds & Ends/116. What Really Matters In This Section\|116. What Really Matters In This Section]] |
> > > | section 14 - Git Collaboration Workflows | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 14 - Git Collaboration Workflows/126. What Really Matters In This Section\|126. What Really Matters In This Section]] |
> > > | section 15 - Rebasing - The Scariest Git Command | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 15 - Rebasing - The Scariest Git Command/140. What Really Matters In This Section\|140. What Really Matters In This Section]] |
> > > | section 16 - Cleaning Up History With Interactive Rebase | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 16 - Cleaning Up History With Interactive Rebase/147. What Really Matters In This Section\|147. What Really Matters In This Section]] |
> > > | section 17 - Git Tags - Marking Important Moments In History | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 17 - Git Tags - Marking Important Moments In History/152. What Really Matters In This Section\|152. What Really Matters In This Section]] |
> > > | section 18 - Git Behind The Scenes - Hashing & Objects | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 18 - Git Behind The Scenes - Hashing & Objects/163. What Really Matters In This Section\|163. What Really Matters In This Section]] |
> > > | section 19 - The Power of Reflogs - Retrieving Lost Work | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 19 - The Power of Reflogs - Retrieving Lost Work/175. What Really Matters In This Section\|175. What Really Matters In This Section]] |
> > > | section 2 - Introducing...Git! | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 2 - Introducing...Git!/10. Who Uses Git\|10. Who Uses Git]] |
> > > | section 20 - Writing Custom Git Aliases | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 20 - Writing Custom Git Aliases/183. What Matters In This Section\|183. What Matters In This Section]] |
> > > | section 3 - Installation & Setup | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 3 - Installation & Setup/12. What Really Matters In This Section\|12. What Really Matters In This Section]] |
> > > | section 4 - The Very Basics Of Git - Adding & Committing | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 4 - The Very Basics Of Git - Adding & Committing/22. What Really Matters In This Section\|22. What Really Matters In This Section]] |
> > > | section 5 - Commits In Detail (And Related Topics) | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 5 - Commits In Detail (And Related Topics)/32. What Really Matters In This Section\|32. What Really Matters In This Section]] |
> > > | section 6 - Working With Branches | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 6 - Working With Branches/41. What Really Matters In This Section\|41. What Really Matters In This Section]] |
> > > | section 7 - Merging Branches, Oh Boy! | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 7 - Merging Branches, Oh Boy!/53. What Really Matters In This Section\|53. What Really Matters In This Section]] |
> > > | section 8 - Comparing Changes With Git Diff | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 8 - Comparing Changes With Git Diff/62. What Really Matters In This Section\|62. What Really Matters In This Section]] |
> > > | section 9 - The Ins and Outs of Stashing | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 9 - The Ins and Outs of Stashing/73. What Really Matters In This Section\|73. What Really Matters In This Section]] |
> > > 
> > > > [!g-white]- section 1 - Course Orientation
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | section 1 - Course Orientation | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 1 - Course Orientation/1. Welcome To The Course!\|1. Welcome To The Course!]] |
> > > > 
> > > 
> > > > [!g-white]- section 10 - Undoing Changes & Time Traveling
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | section 10 - Undoing Changes & Time Traveling | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 10 - Undoing Changes & Time Traveling/81. What Really Matters In This Section\|81. What Really Matters In This Section]] |
> > > > 
> > > 
> > > > [!g-white]- section 11 - Github - The Basics
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | section 11 - Github - The Basics | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 11 - Github - The Basics/100. Touring A Github Repo\|100. Touring A Github Repo]] |
> > > > 
> > > 
> > > > [!g-white]- section 12 - Fetching & Pulling
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | section 12 - Fetching & Pulling | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 12 - Fetching & Pulling/107. What Really Matters In This Section\|107. What Really Matters In This Section]] |
> > > > 
> > > 
> > > > [!g-white]- section 13 - Github Grab Bag - Odds & Ends
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | section 13 - Github Grab Bag - Odds & Ends | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 13 - Github Grab Bag - Odds & Ends/116. What Really Matters In This Section\|116. What Really Matters In This Section]] |
> > > > 
> > > 
> > > > [!g-white]- section 14 - Git Collaboration Workflows
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | section 14 - Git Collaboration Workflows | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 14 - Git Collaboration Workflows/126. What Really Matters In This Section\|126. What Really Matters In This Section]] |
> > > > 
> > > 
> > > > [!g-white]- section 15 - Rebasing - The Scariest Git Command
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | section 15 - Rebasing - The Scariest Git Command | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 15 - Rebasing - The Scariest Git Command/140. What Really Matters In This Section\|140. What Really Matters In This Section]] |
> > > > 
> > > 
> > > > [!g-white]- section 16 - Cleaning Up History With Interactive Rebase
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | section 16 - Cleaning Up History With Interactive Rebase | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 16 - Cleaning Up History With Interactive Rebase/147. What Really Matters In This Section\|147. What Really Matters In This Section]] |
> > > > 
> > > 
> > > > [!g-white]- section 17 - Git Tags - Marking Important Moments In History
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | section 17 - Git Tags - Marking Important Moments In History | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 17 - Git Tags - Marking Important Moments In History/152. What Really Matters In This Section\|152. What Really Matters In This Section]] |
> > > > 
> > > 
> > > > [!g-white]- section 18 - Git Behind The Scenes - Hashing & Objects
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | section 18 - Git Behind The Scenes - Hashing & Objects | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 18 - Git Behind The Scenes - Hashing & Objects/163. What Really Matters In This Section\|163. What Really Matters In This Section]] |
> > > > 
> > > 
> > > > [!g-white]- section 19 - The Power of Reflogs - Retrieving Lost Work
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | section 19 - The Power of Reflogs - Retrieving Lost Work | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 19 - The Power of Reflogs - Retrieving Lost Work/175. What Really Matters In This Section\|175. What Really Matters In This Section]] |
> > > > 
> > > 
> > > > [!g-white]- section 2 - Introducing...Git!
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | section 2 - Introducing...Git! | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 2 - Introducing...Git!/10. Who Uses Git\|10. Who Uses Git]] |
> > > > 
> > > 
> > > > [!g-white]- section 20 - Writing Custom Git Aliases
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | section 20 - Writing Custom Git Aliases | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 20 - Writing Custom Git Aliases/183. What Matters In This Section\|183. What Matters In This Section]] |
> > > > 
> > > 
> > > > [!g-white]- section 3 - Installation & Setup
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | section 3 - Installation & Setup | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 3 - Installation & Setup/12. What Really Matters In This Section\|12. What Really Matters In This Section]] |
> > > > 
> > > 
> > > > [!g-white]- section 4 - The Very Basics Of Git - Adding & Committing
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | section 4 - The Very Basics Of Git - Adding & Committing | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 4 - The Very Basics Of Git - Adding & Committing/22. What Really Matters In This Section\|22. What Really Matters In This Section]] |
> > > > 
> > > 
> > > > [!g-white]- section 5 - Commits In Detail (And Related Topics)
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | section 5 - Commits In Detail (And Related Topics) | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 5 - Commits In Detail (And Related Topics)/32. What Really Matters In This Section\|32. What Really Matters In This Section]] |
> > > > 
> > > 
> > > > [!g-white]- section 6 - Working With Branches
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | section 6 - Working With Branches | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 6 - Working With Branches/41. What Really Matters In This Section\|41. What Really Matters In This Section]] |
> > > > 
> > > 
> > > > [!g-white]- section 7 - Merging Branches, Oh Boy!
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | section 7 - Merging Branches, Oh Boy! | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 7 - Merging Branches, Oh Boy!/53. What Really Matters In This Section\|53. What Really Matters In This Section]] |
> > > > 
> > > 
> > > > [!g-white]- section 8 - Comparing Changes With Git Diff
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | section 8 - Comparing Changes With Git Diff | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 8 - Comparing Changes With Git Diff/62. What Really Matters In This Section\|62. What Really Matters In This Section]] |
> > > > 
> > > 
> > > > [!g-white]- section 9 - The Ins and Outs of Stashing
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | section 9 - The Ins and Outs of Stashing | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 9 - The Ins and Outs of Stashing/73. What Really Matters In This Section\|73. What Really Matters In This Section]] |
> > > >
<!-- Git and Github_END -->

<!-- Miscellaneous_START -->
> [!g-gray] Miscellaneous
> 
> > [!multi-column]
> > 
> > 
> > No files
> > 
> > > [!g-white]- AI PC setup
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | AI PC setup | [[Learning/Programming/Miscellaneous/AI PC setup/EPYC 9335 build\|EPYC 9335 build]] |
> > > | LLAMA3 | [[Learning/Programming/Miscellaneous/AI PC setup/LLAMA3/Calculating GPU memory for serving LLMs\|Calculating GPU memory for serving LLMs]] |
> > > | Write my book on it | [[Learning/Programming/Miscellaneous/AI PC setup/Write my book on it/1. Building a ML&AI Computer System - Chapter 1 - Introduction\|1. Building a ML&AI Computer System - Chapter 1 - Introduction]] |
> > > 
> > > > [!g-white]- LLAMA3
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | LLAMA3 | [[Learning/Programming/Miscellaneous/AI PC setup/LLAMA3/Calculating GPU memory for serving LLMs\|Calculating GPU memory for serving LLMs]] |
> > > > 
> > > 
> > > > [!g-white]- Write my book on it
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Write my book on it | [[Learning/Programming/Miscellaneous/AI PC setup/Write my book on it/1. Building a ML&AI Computer System - Chapter 1 - Introduction\|1. Building a ML&AI Computer System - Chapter 1 - Introduction]] |
> > > > 
> > 
> > > [!g-white]- RHCSA, RHCE
> > > 
> > > 
> > > > [!g-white]- books
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | books | [[Learning/Programming/Miscellaneous/RHCSA, RHCE/books/Red Hat RHCSA 9 Cert Guide - EX200 by Sander van Vugt\|Red Hat RHCSA 9 Cert Guide - EX200 by Sander van Vugt]] |
> > > > 
> > 
> > > [!g-white]- RHEL 9
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | RHEL 9 | [[Learning/Programming/Miscellaneous/RHEL 9/Configuring samba\|Configuring samba]] |
> > > | tests | [[Learning/Programming/Miscellaneous/RHEL 9/tests/Tutorial on git\|Tutorial on git]] |
> > > 
> > > > [!g-white]- tests
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | tests | [[Learning/Programming/Miscellaneous/RHEL 9/tests/Tutorial on git\|Tutorial on git]] |
> > > > 
> > 
> > > [!g-white]- Usefull information, Problems and KYC
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | Usefull information, Problems and KYC | [[Learning/Programming/Miscellaneous/Usefull information, Problems and KYC/Clone drives and partitions to another drive\|Clone drives and partitions to another drive]] |
> > > | epub editing | [[Learning/Programming/Miscellaneous/Usefull information, Problems and KYC/epub editing/creating expandable\|creating expandable]] |
> > > | Income tax efiling | [[Learning/Programming/Miscellaneous/Usefull information, Problems and KYC/Income tax efiling/Section 1 - Introduction/1. Introduction\|1. Introduction]] |
> > > | Kasm workspaces with cloudflare | [[Learning/Programming/Miscellaneous/Usefull information, Problems and KYC/Kasm workspaces with cloudflare/Allow origin Domain and Upstream Auth Address\|Allow origin Domain and Upstream Auth Address]] |
> > > | linux problems and tasks | [[Learning/Programming/Miscellaneous/Usefull information, Problems and KYC/linux problems and tasks/Custom icons\|Custom icons]] |
> > > 
> > > > [!g-white]- epub editing
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | epub editing | [[Learning/Programming/Miscellaneous/Usefull information, Problems and KYC/epub editing/creating expandable\|creating expandable]] |
> > > > 
> > > 
> > > > [!g-white]- Income tax efiling
> > > > 
> > > > 
> > > > > [!g-white]- Section 1 - Introduction
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 1 - Introduction | [[Learning/Programming/Miscellaneous/Usefull information, Problems and KYC/Income tax efiling/Section 1 - Introduction/1. Introduction\|1. Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 2 - E-Filing Basics
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 2 - E-Filing Basics | [[Learning/Programming/Miscellaneous/Usefull information, Problems and KYC/Income tax efiling/Section 2 - E-Filing Basics/2. Introduction to e-Filing Portal & Income Tax Utilities\|2. Introduction to e-Filing Portal & Income Tax Utilities]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 3 - Individual Tax Return Filing
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 3 - Individual Tax Return Filing | [[Learning/Programming/Miscellaneous/Usefull information, Problems and KYC/Income tax efiling/Section 3 - Individual Tax Return Filing/3. ITR-1-Online and Offline Filing\|3. ITR-1-Online and Offline Filing]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 4 - Advanced Tax Topics
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 4 - Advanced Tax Topics | [[Learning/Programming/Miscellaneous/Usefull information, Problems and KYC/Income tax efiling/Section 4 - Advanced Tax Topics/10. Selection of ITR Forms in Detail and Form 29B\|10. Selection of ITR Forms in Detail and Form 29B]] |
> > > > > 
> > > 
> > > > [!g-white]- Kasm workspaces with cloudflare
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Kasm workspaces with cloudflare | [[Learning/Programming/Miscellaneous/Usefull information, Problems and KYC/Kasm workspaces with cloudflare/Allow origin Domain and Upstream Auth Address\|Allow origin Domain and Upstream Auth Address]] |
> > > > 
> > > 
> > > > [!g-white]- linux problems and tasks
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | linux problems and tasks | [[Learning/Programming/Miscellaneous/Usefull information, Problems and KYC/linux problems and tasks/Custom icons\|Custom icons]] |
> > > > | Linux problems and resolutions | [[Learning/Programming/Miscellaneous/Usefull information, Problems and KYC/linux problems and tasks/Linux problems and resolutions/Bridged network for guest KVM's\|Bridged network for guest KVM's]] |
> > > > 
> > > > > [!g-white]- Image slider
> > > > > 
> > > > > 
> > > > 
> > > > > [!g-white]- Linux problems and resolutions
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Linux problems and resolutions | [[Learning/Programming/Miscellaneous/Usefull information, Problems and KYC/linux problems and tasks/Linux problems and resolutions/Bridged network for guest KVM's\|Bridged network for guest KVM's]] |
> > > > >
<!-- Miscellaneous_END -->

<!-- Python_START -->
> [!g-gray] Python
> 
> > [!multi-column]
> > 
> > 
> > 
> > | Folder | First File Link |
> > | --- | --- |
> > |  | [[Learning/Programming/Python/Other python links in vault\|Other python links in vault]] |
> > 
> > > [!g-white]- Automate Excel Using Python
> > > 
> > > 
> > > > [!g-white]- Section 1 - Introduction
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 1 - Introduction | [[Learning/Programming/Python/Automate Excel Using Python/Section 1 - Introduction/1. Introduction\|1. Introduction]] |
> > > > 
> > > 
> > > > [!g-white]- Section 10 - Add Formulas
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 10 - Add Formulas | [[Learning/Programming/Python/Automate Excel Using Python/Section 10 - Add Formulas/45. Add Formulas to the cell\|45. Add Formulas to the cell]] |
> > > > 
> > > 
> > > > [!g-white]- Section 11 - Filter Operations
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 11 - Filter Operations | [[Learning/Programming/Python/Automate Excel Using Python/Section 11 - Filter Operations/46. Filter Operations.\|46. Filter Operations.]] |
> > > > 
> > > 
> > > > [!g-white]- Section 12 - Charts
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 12 - Charts | [[Learning/Programming/Python/Automate Excel Using Python/Section 12 - Charts/47. Create Pie Charts\|47. Create Pie Charts]] |
> > > > 
> > > 
> > > > [!g-white]- Section 13 - Manipulating Worksheet
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 13 - Manipulating Worksheet | [[Learning/Programming/Python/Automate Excel Using Python/Section 13 - Manipulating Worksheet/52. Deleting Rows and Columns\|52. Deleting Rows and Columns]] |
> > > > 
> > > 
> > > > [!g-white]- Section 14 - Data Iterating
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 14 - Data Iterating | [[Learning/Programming/Python/Automate Excel Using Python/Section 14 - Data Iterating/54. Iterating Data of Columns and Rows.\|54. Iterating Data of Columns and Rows.]] |
> > > > 
> > > 
> > > > [!g-white]- Section 15 - Read and Write Operations from different files
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 15 - Read and Write Operations from different files | [[Learning/Programming/Python/Automate Excel Using Python/Section 15 - Read and Write Operations from different files/56. Copy Data from one sheet to another sheet.\|56. Copy Data from one sheet to another sheet.]] |
> > > > 
> > > 
> > > > [!g-white]- Section 2 - Configuration softwares for Windows and Mac
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 2 - Configuration softwares for Windows and Mac | [[Learning/Programming/Python/Automate Excel Using Python/Section 2 - Configuration softwares for Windows and Mac/2. List of softwares required for configuration\|2. List of softwares required for configuration]] |
> > > > 
> > > 
> > > > [!g-white]- Section 3 - Python Basics
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 3 - Python Basics | [[Learning/Programming/Python/Automate Excel Using Python/Section 3 - Python Basics/10. Variables\|10. Variables]] |
> > > > 
> > > 
> > > > [!g-white]- Section 4 - Overview on Workbook and Worksheet
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 4 - Overview on Workbook and Worksheet | [[Learning/Programming/Python/Automate Excel Using Python/Section 4 - Overview on Workbook and Worksheet/30. Create Workbook and Worksheet\|30. Create Workbook and Worksheet]] |
> > > > 
> > > 
> > > > [!g-white]- Section 5 - Write Operations
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 5 - Write Operations | [[Learning/Programming/Python/Automate Excel Using Python/Section 5 - Write Operations/33. Write the data in cells\|33. Write the data in cells]] |
> > > > 
> > > 
> > > > [!g-white]- Section 6 - Read Operations
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 6 - Read Operations | [[Learning/Programming/Python/Automate Excel Using Python/Section 6 - Read Operations/35. Read the data from the Excel file.\|35. Read the data from the Excel file.]] |
> > > > 
> > > 
> > > > [!g-white]- Section 7 - Comments in Excel sheet
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 7 - Comments in Excel sheet | [[Learning/Programming/Python/Automate Excel Using Python/Section 7 - Comments in Excel sheet/38. Add the comments to the cell.\|38. Add the comments to the cell.]] |
> > > > 
> > > 
> > > > [!g-white]- Section 8 - Add Styles to Excel sheet data
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 8 - Add Styles to Excel sheet data | [[Learning/Programming/Python/Automate Excel Using Python/Section 8 - Add Styles to Excel sheet data/39. Part 1 - Styles to the text data in Excel sheet - Bold , Italic ,Underline, etc\|39. Part 1 - Styles to the text data in Excel sheet - Bold , Italic ,Underline, etc]] |
> > > > 
> > > 
> > > > [!g-white]- Section 9 - Add Image to excel file
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 9 - Add Image to excel file | [[Learning/Programming/Python/Automate Excel Using Python/Section 9 - Add Image to excel file/44. Add image to excel file.\|44. Add image to excel file.]] |
> > > > 
> > 
> > > [!g-white]- Automating networks
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | Automating networks | [[Learning/Programming/Python/Automating networks/Automating networks\|Automating networks]] |
> > > | Master Network Automation with Python for Network Engineers | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Master Network Automation with Python for Network Engineers\|Master Network Automation with Python for Network Engineers]] |
> > > | Mastering Python Networking | [[Learning/Programming/Python/Automating networks/Mastering Python Networking/Mastering Python Networking\|Mastering Python Networking]] |
> > > | Python Programming for Network Engineers - Cisco, Netmiko ++ | [[Learning/Programming/Python/Automating networks/Python Programming for Network Engineers - Cisco, Netmiko ++/Python Programming for Network Engineers - Cisco, Netmiko ++\|Python Programming for Network Engineers - Cisco, Netmiko ++]] |
> > > 
> > > > [!g-white]- Master Network Automation with Python for Network Engineers
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Master Network Automation with Python for Network Engineers | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Master Network Automation with Python for Network Engineers\|Master Network Automation with Python for Network Engineers]] |
> > > > | Section 1 - Course Introduction | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 1 - Course Introduction/1. Why Network Automation with Python Why Now\|1. Why Network Automation with Python Why Now]] |
> > > > | Section 10 - Building Concurrent Applications Using Async IO | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 10 - Building Concurrent Applications Using Async IO/100. Coding - Running Shell Commands\|100. Coding - Running Shell Commands]] |
> > > > | Section 11 - [Appendix] - Running Arista vEOS and Juniper vSRX in GNS3 | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 11 - [Appendix] - Running Arista vEOS and Juniper vSRX in GNS3/104. How to Run Arista vEOS in GNS3\|104. How to Run Arista vEOS in GNS3]] |
> > > > | Section 12 - Network Automation with Napalm | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 12 - Network Automation with Napalm/110. Intro to Napalm\|110. Intro to Napalm]] |
> > > > | Section 13 - Network Automation with Telnet | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 13 - Network Automation with Telnet/118. Bytes Objects, Encoding and Decoding\|118. Bytes Objects, Encoding and Decoding]] |
> > > > | Section 14 - Hands-On Challenges - Network Automation with Telnet | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 14 - Hands-On Challenges - Network Automation with Telnet/127. Hands-On Challenges - Telnet\|127. Hands-On Challenges - Telnet]] |
> > > > | Section 15 - Network Automation Using Serial Connections | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 15 - Network Automation Using Serial Connections/128. Serial Communication Basics. Connecting to a Console Port\|128. Serial Communication Basics. Connecting to a Console Port]] |
> > > > | Section 16 - [Appendix] Useful Python Modules | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 16 - [Appendix] Useful Python Modules/135. System-specific Parameters and Functions - The Sys Module\|135. System-specific Parameters and Functions - The Sys Module]] |
> > > > | Section 17 - [Appendix] - SSH Public Key Authentication (Cisco IOS & Linux) | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 17 - [Appendix] - SSH Public Key Authentication (Cisco IOS & Linux)/140. SSH Public Key Authentication Overview\|140. SSH Public Key Authentication Overview]] |
> > > > | Section 18 - [Appendix] - Ansible - Automate for Everyone | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 18 - [Appendix] - Ansible - Automate for Everyone/147. About This Section\|147. About This Section]] |
> > > > | Section 19 - [Appendix] - Ansible Playbooks | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 19 - [Appendix] - Ansible Playbooks/157. YAML Files\|157. YAML Files]] |
> > > > | Section 2 - Setup the Environment - Python, PyCharm, GNS3, Cisco IOU and | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 2 - Setup the Environment - Python, PyCharm, GNS3, Cisco IOU and/10. Installing Python 3 on Windows\|10. Installing Python 3 on Windows]] |
> > > > | Section 20 - [Python Programming] - Python Basics | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 20 - [Python Programming] - Python Basics/172. Quick Note for Beginners\|172. Quick Note for Beginners]] |
> > > > | Section 21 - [Python Programming] - Strings in Python | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 21 - [Python Programming] - Strings in Python/186. Intro to Strings\|186. Intro to Strings]] |
> > > > | Section 22 - [Python Programming] - Program Flow Control | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 22 - [Python Programming] - Program Flow Control/195. Conditional Statements\|195. Conditional Statements]] |
> > > > | Section 23 - [Python Programming] Python Loops | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 23 - [Python Programming] Python Loops/201. For Loops\|201. For Loops]] |
> > > > | Section 24 - [Python Programming] - Lists and Tuples in Python | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 24 - [Python Programming] - Lists and Tuples in Python/211. Intro to Lists\|211. Intro to Lists]] |
> > > > | Section 25 - [Python Programming] - Sets, Frozensets and Dictionaries in Python | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 25 - [Python Programming] - Sets, Frozensets and Dictionaries in Python/223. Intro to Sets\|223. Intro to Sets]] |
> > > > | Section 26 - [Python Programming] - Functions in Python | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 26 - [Python Programming] - Functions in Python/232. Intro to Functions\|232. Intro to Functions]] |
> > > > | Section 27 - [Python Programming] - Errors and Exception Handling | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 27 - [Python Programming] - Errors and Exception Handling/241. Intro to Exceptions\|241. Intro to Exceptions]] |
> > > > | Section 28 - [Python Programming] - Object Oriented Programming Basics | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 28 - [Python Programming] - Object Oriented Programming Basics/245. Intro to Object Oriented Programming\|245. Intro to Object Oriented Programming]] |
> > > > | Section 29 - BONUS SECTION | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 29 - BONUS SECTION/251. Congratulations\|251. Congratulations]] |
> > > > | Section 3 - Working with Text Files In Python | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 3 - Working with Text Files In Python/26. Intro\|26. Intro]] |
> > > > | Section 4 - Hands-On Challenges - Working With Files | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 4 - Hands-On Challenges - Working With Files/42. Hands-On Challenges - Working with Text Files\|42. Hands-On Challenges - Working with Text Files]] |
> > > > | Section 5 - Data Serialization and Deserialization In Python (Pickle and...) | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 5 - Data Serialization and Deserialization In Python (Pickle and...)/44. Intro to Data Serialization\|44. Intro to Data Serialization]] |
> > > > | Section 6 - Network Automation with Paramiko (SSH) | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 6 - Network Automation with Paramiko (SSH)/56. The Lab Environment\|56. The Lab Environment]] |
> > > > | Section 7 - Hands-On Challenges - Network Automation with Paramiko | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 7 - Hands-On Challenges - Network Automation with Paramiko/76. Hands-On Challenges - Paramiko\|76. Hands-On Challenges - Paramiko]] |
> > > > | Section 8 - Network Automation with Netmiko (SSH) | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 8 - Network Automation with Netmiko (SSH)/77. The Lab Environment\|77. The Lab Environment]] |
> > > > | Section 9 - Hands-On Challenges - Network Automation with Netmiko | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 9 - Hands-On Challenges - Network Automation with Netmiko/93. Hands-On Challenges - Netmiko\|93. Hands-On Challenges - Netmiko]] |
> > > > 
> > > > > [!g-white]- Section 1 - Course Introduction
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 1 - Course Introduction | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 1 - Course Introduction/1. Why Network Automation with Python Why Now\|1. Why Network Automation with Python Why Now]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 10 - Building Concurrent Applications Using Async IO
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 10 - Building Concurrent Applications Using Async IO | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 10 - Building Concurrent Applications Using Async IO/100. Coding - Running Shell Commands\|100. Coding - Running Shell Commands]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 11 - [Appendix] - Running Arista vEOS and Juniper vSRX in GNS3
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 11 - [Appendix] - Running Arista vEOS and Juniper vSRX in GNS3 | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 11 - [Appendix] - Running Arista vEOS and Juniper vSRX in GNS3/104. How to Run Arista vEOS in GNS3\|104. How to Run Arista vEOS in GNS3]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 12 - Network Automation with Napalm
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 12 - Network Automation with Napalm | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 12 - Network Automation with Napalm/110. Intro to Napalm\|110. Intro to Napalm]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 13 - Network Automation with Telnet
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 13 - Network Automation with Telnet | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 13 - Network Automation with Telnet/118. Bytes Objects, Encoding and Decoding\|118. Bytes Objects, Encoding and Decoding]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 14 - Hands-On Challenges - Network Automation with Telnet
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 14 - Hands-On Challenges - Network Automation with Telnet | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 14 - Hands-On Challenges - Network Automation with Telnet/127. Hands-On Challenges - Telnet\|127. Hands-On Challenges - Telnet]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 15 - Network Automation Using Serial Connections
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 15 - Network Automation Using Serial Connections | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 15 - Network Automation Using Serial Connections/128. Serial Communication Basics. Connecting to a Console Port\|128. Serial Communication Basics. Connecting to a Console Port]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 16 - [Appendix] Useful Python Modules
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 16 - [Appendix] Useful Python Modules | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 16 - [Appendix] Useful Python Modules/135. System-specific Parameters and Functions - The Sys Module\|135. System-specific Parameters and Functions - The Sys Module]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 17 - [Appendix] - SSH Public Key Authentication (Cisco IOS & Linux)
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 17 - [Appendix] - SSH Public Key Authentication (Cisco IOS & Linux) | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 17 - [Appendix] - SSH Public Key Authentication (Cisco IOS & Linux)/140. SSH Public Key Authentication Overview\|140. SSH Public Key Authentication Overview]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 18 - [Appendix] - Ansible - Automate for Everyone
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 18 - [Appendix] - Ansible - Automate for Everyone | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 18 - [Appendix] - Ansible - Automate for Everyone/147. About This Section\|147. About This Section]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 19 - [Appendix] - Ansible Playbooks
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 19 - [Appendix] - Ansible Playbooks | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 19 - [Appendix] - Ansible Playbooks/157. YAML Files\|157. YAML Files]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 2 - Setup the Environment - Python, PyCharm, GNS3, Cisco IOU and
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 2 - Setup the Environment - Python, PyCharm, GNS3, Cisco IOU and | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 2 - Setup the Environment - Python, PyCharm, GNS3, Cisco IOU and/10. Installing Python 3 on Windows\|10. Installing Python 3 on Windows]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 20 - [Python Programming] - Python Basics
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 20 - [Python Programming] - Python Basics | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 20 - [Python Programming] - Python Basics/172. Quick Note for Beginners\|172. Quick Note for Beginners]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 21 - [Python Programming] - Strings in Python
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 21 - [Python Programming] - Strings in Python | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 21 - [Python Programming] - Strings in Python/186. Intro to Strings\|186. Intro to Strings]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 22 - [Python Programming] - Program Flow Control
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 22 - [Python Programming] - Program Flow Control | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 22 - [Python Programming] - Program Flow Control/195. Conditional Statements\|195. Conditional Statements]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 23 - [Python Programming] Python Loops
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 23 - [Python Programming] Python Loops | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 23 - [Python Programming] Python Loops/201. For Loops\|201. For Loops]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 24 - [Python Programming] - Lists and Tuples in Python
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 24 - [Python Programming] - Lists and Tuples in Python | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 24 - [Python Programming] - Lists and Tuples in Python/211. Intro to Lists\|211. Intro to Lists]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 25 - [Python Programming] - Sets, Frozensets and Dictionaries in Python
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 25 - [Python Programming] - Sets, Frozensets and Dictionaries in Python | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 25 - [Python Programming] - Sets, Frozensets and Dictionaries in Python/223. Intro to Sets\|223. Intro to Sets]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 26 - [Python Programming] - Functions in Python
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 26 - [Python Programming] - Functions in Python | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 26 - [Python Programming] - Functions in Python/232. Intro to Functions\|232. Intro to Functions]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 27 - [Python Programming] - Errors and Exception Handling
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 27 - [Python Programming] - Errors and Exception Handling | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 27 - [Python Programming] - Errors and Exception Handling/241. Intro to Exceptions\|241. Intro to Exceptions]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 28 - [Python Programming] - Object Oriented Programming Basics
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 28 - [Python Programming] - Object Oriented Programming Basics | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 28 - [Python Programming] - Object Oriented Programming Basics/245. Intro to Object Oriented Programming\|245. Intro to Object Oriented Programming]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 29 - BONUS SECTION
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 29 - BONUS SECTION | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 29 - BONUS SECTION/251. Congratulations\|251. Congratulations]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 3 - Working with Text Files In Python
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 3 - Working with Text Files In Python | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 3 - Working with Text Files In Python/26. Intro\|26. Intro]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 4 - Hands-On Challenges - Working With Files
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 4 - Hands-On Challenges - Working With Files | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 4 - Hands-On Challenges - Working With Files/42. Hands-On Challenges - Working with Text Files\|42. Hands-On Challenges - Working with Text Files]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 5 - Data Serialization and Deserialization In Python (Pickle and...)
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 5 - Data Serialization and Deserialization In Python (Pickle and...) | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 5 - Data Serialization and Deserialization In Python (Pickle and...)/44. Intro to Data Serialization\|44. Intro to Data Serialization]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 6 - Network Automation with Paramiko (SSH)
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 6 - Network Automation with Paramiko (SSH) | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 6 - Network Automation with Paramiko (SSH)/56. The Lab Environment\|56. The Lab Environment]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 7 - Hands-On Challenges - Network Automation with Paramiko
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 7 - Hands-On Challenges - Network Automation with Paramiko | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 7 - Hands-On Challenges - Network Automation with Paramiko/76. Hands-On Challenges - Paramiko\|76. Hands-On Challenges - Paramiko]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 8 - Network Automation with Netmiko (SSH)
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 8 - Network Automation with Netmiko (SSH) | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 8 - Network Automation with Netmiko (SSH)/77. The Lab Environment\|77. The Lab Environment]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 9 - Hands-On Challenges - Network Automation with Netmiko
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 9 - Hands-On Challenges - Network Automation with Netmiko | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 9 - Hands-On Challenges - Network Automation with Netmiko/93. Hands-On Challenges - Netmiko\|93. Hands-On Challenges - Netmiko]] |
> > > > > 
> > > 
> > > > [!g-white]- Mastering Python Networking
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Mastering Python Networking | [[Learning/Programming/Python/Automating networks/Mastering Python Networking/Mastering Python Networking\|Mastering Python Networking]] |
> > > > | Section 1 - Python Network Programming | [[Learning/Programming/Python/Automating networks/Mastering Python Networking/Section 1 - Python Network Programming/1. The Course Overview\|1. The Course Overview]] |
> > > > | Section 2 - Hands-on Network Programming with Python | [[Learning/Programming/Python/Automating networks/Mastering Python Networking/Section 2 - Hands-on Network Programming with Python/20. The Course Overview\|20. The Course Overview]] |
> > > > 
> > > > > [!g-white]- Section 1 - Python Network Programming
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 1 - Python Network Programming | [[Learning/Programming/Python/Automating networks/Mastering Python Networking/Section 1 - Python Network Programming/1. The Course Overview\|1. The Course Overview]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 2 - Hands-on Network Programming with Python
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 2 - Hands-on Network Programming with Python | [[Learning/Programming/Python/Automating networks/Mastering Python Networking/Section 2 - Hands-on Network Programming with Python/20. The Course Overview\|20. The Course Overview]] |
> > > > > 
> > > 
> > > > [!g-white]- Python Programming for Network Engineers - Cisco, Netmiko ++
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Python Programming for Network Engineers - Cisco, Netmiko ++ | [[Learning/Programming/Python/Automating networks/Python Programming for Network Engineers - Cisco, Netmiko ++/Python Programming for Network Engineers - Cisco, Netmiko ++\|Python Programming for Network Engineers - Cisco, Netmiko ++]] |
> > > > | Section 1 - Introduction | [[Learning/Programming/Python/Automating networks/Python Programming for Network Engineers - Cisco, Netmiko ++/Section 1 - Introduction/1.  Good news!\|1.  Good news!]] |
> > > > | Section 2 - GNS3 Setup | [[Learning/Programming/Python/Automating networks/Python Programming for Network Engineers - Cisco, Netmiko ++/Section 2 - GNS3 Setup/10. EVE-NG Cisco Images\|10. EVE-NG Cisco Images]] |
> > > > | Section 3 - Network Programmability with Python | [[Learning/Programming/Python/Automating networks/Python Programming for Network Engineers - Cisco, Netmiko ++/Section 3 - Network Programmability with Python/12. (Part 1) Network programmability made easy.\|12. (Part 1) Network programmability made easy.]] |
> > > > | Section 4 - Network Automation Appliance | [[Learning/Programming/Python/Automating networks/Python Programming for Network Engineers - Cisco, Netmiko ++/Section 4 - Network Automation Appliance/30. GNS3 Automation Container import and testing Part 1\|30. GNS3 Automation Container import and testing Part 1]] |
> > > > 
> > > > > [!g-white]- Section 1 - Introduction
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 1 - Introduction | [[Learning/Programming/Python/Automating networks/Python Programming for Network Engineers - Cisco, Netmiko ++/Section 1 - Introduction/1.  Good news!\|1.  Good news!]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 2 - GNS3 Setup
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 2 - GNS3 Setup | [[Learning/Programming/Python/Automating networks/Python Programming for Network Engineers - Cisco, Netmiko ++/Section 2 - GNS3 Setup/10. EVE-NG Cisco Images\|10. EVE-NG Cisco Images]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 3 - Network Programmability with Python
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 3 - Network Programmability with Python | [[Learning/Programming/Python/Automating networks/Python Programming for Network Engineers - Cisco, Netmiko ++/Section 3 - Network Programmability with Python/12. (Part 1) Network programmability made easy.\|12. (Part 1) Network programmability made easy.]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 4 - Network Automation Appliance
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 4 - Network Automation Appliance | [[Learning/Programming/Python/Automating networks/Python Programming for Network Engineers - Cisco, Netmiko ++/Section 4 - Network Automation Appliance/30. GNS3 Automation Container import and testing Part 1\|30. GNS3 Automation Container import and testing Part 1]] |
> > > > > 
> > 
> > > [!g-white]- Certification
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | Certification | [[Learning/Programming/Python/Certification/Certification\|Certification]] |
> > > 
> > 
> > > [!g-white]- chatGPT
> > > 
> > > 
> > > > [!g-white]- unit testing
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | unit testing | [[Learning/Programming/Python/chatGPT/unit testing/Untitled\|Untitled]] |
> > > > 
> > 
> > > [!g-white]- Concurrent and Parallel Programming in Python
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | Concurrent and Parallel Programming in Python | [[Learning/Programming/Python/Concurrent and Parallel Programming in Python/Concurrent and Parallel Programming in Python\|Concurrent and Parallel Programming in Python]] |
> > > | Extra info | [[Learning/Programming/Python/Concurrent and Parallel Programming in Python/Extra info/Process vs Thread\|Process vs Thread]] |
> > > | Section 1 - Threading | [[Learning/Programming/Python/Concurrent and Parallel Programming in Python/Section 1 - Threading/1. Threading, Multiprocessing, Async Intro\|1. Threading, Multiprocessing, Async Intro]] |
> > > | Section 1 - Threading (Copy) | [[Learning/Programming/Python/Concurrent and Parallel Programming in Python/Section 1 - Threading (Copy)/1. Threading, Multiprocessing, Async Intro\|1. Threading, Multiprocessing, Async Intro]] |
> > > | Section 2 - Multiprocessing | [[Learning/Programming/Python/Concurrent and Parallel Programming in Python/Section 2 - Multiprocessing/15. Multiprocessing Intro\|15. Multiprocessing Intro]] |
> > > | Section 3 - Asynchronous | [[Learning/Programming/Python/Concurrent and Parallel Programming in Python/Section 3 - Asynchronous/21. Intro to Writing Asynchronous Programs\|21. Intro to Writing Asynchronous Programs]] |
> > > 
> > > > [!g-white]- Extra info
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Extra info | [[Learning/Programming/Python/Concurrent and Parallel Programming in Python/Extra info/Process vs Thread\|Process vs Thread]] |
> > > > 
> > > 
> > > > [!g-white]- Section 1 - Threading
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 1 - Threading | [[Learning/Programming/Python/Concurrent and Parallel Programming in Python/Section 1 - Threading/1. Threading, Multiprocessing, Async Intro\|1. Threading, Multiprocessing, Async Intro]] |
> > > > 
> > > 
> > > > [!g-white]- Section 1 - Threading (Copy)
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 1 - Threading (Copy) | [[Learning/Programming/Python/Concurrent and Parallel Programming in Python/Section 1 - Threading (Copy)/1. Threading, Multiprocessing, Async Intro\|1. Threading, Multiprocessing, Async Intro]] |
> > > > 
> > > 
> > > > [!g-white]- Section 2 - Multiprocessing
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 2 - Multiprocessing | [[Learning/Programming/Python/Concurrent and Parallel Programming in Python/Section 2 - Multiprocessing/15. Multiprocessing Intro\|15. Multiprocessing Intro]] |
> > > > 
> > > 
> > > > [!g-white]- Section 3 - Asynchronous
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 3 - Asynchronous | [[Learning/Programming/Python/Concurrent and Parallel Programming in Python/Section 3 - Asynchronous/21. Intro to Writing Asynchronous Programs\|21. Intro to Writing Asynchronous Programs]] |
> > > > 
> > 
> > > [!g-white]- Data Visualisation
> > > 
> > > 
> > > > [!g-white]- Data Visualization with Python and Matplotlib
> > > > 
> > > > 
> > > > > [!g-white]- Section 1- Course Introduction
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 1- Course Introduction | [[Learning/Programming/Python/Data Visualisation/Data Visualization with Python and Matplotlib/Section 1- Course Introduction/1. Introduction\|1. Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 2- Different types of basic Matplotlib charts
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 2- Different types of basic Matplotlib charts | [[Learning/Programming/Python/Data Visualisation/Data Visualization with Python and Matplotlib/Section 2- Different types of basic Matplotlib charts/10. Stack Plots\|10. Stack Plots]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 3- Basic customization options
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 3- Basic customization options | [[Learning/Programming/Python/Data Visualisation/Data Visualization with Python and Matplotlib/Section 3- Basic customization options/15. Section Intro\|15. Section Intro]] |
> > > > > 
> > > 
> > > > [!g-white]- Plotly
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Plotly | [[Learning/Programming/Python/Data Visualisation/Plotly/Topics\|Topics]] |
> > > > | 1. Getting_Started | [[Learning/Programming/Python/Data Visualisation/Plotly/1. Getting_Started/First_Plot_with_Plotly\|First_Plot_with_Plotly]] |
> > > > | 2. Basic_Plots | [[Learning/Programming/Python/Data Visualisation/Plotly/2. Basic_Plots/Scatter_Plots\|Scatter_Plots]] |
> > > > | 3. Customization | [[Learning/Programming/Python/Data Visualisation/Plotly/3. Customization/Annotations_and_Text\|Annotations_and_Text]] |
> > > > 
> > > > > [!g-white]- 1. Getting_Started
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | 1. Getting_Started | [[Learning/Programming/Python/Data Visualisation/Plotly/1. Getting_Started/First_Plot_with_Plotly\|First_Plot_with_Plotly]] |
> > > > > 
> > > > 
> > > > > [!g-white]- 2. Basic_Plots
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | 2. Basic_Plots | [[Learning/Programming/Python/Data Visualisation/Plotly/2. Basic_Plots/Scatter_Plots\|Scatter_Plots]] |
> > > > > 
> > > > 
> > > > > [!g-white]- 3. Customization
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | 3. Customization | [[Learning/Programming/Python/Data Visualisation/Plotly/3. Customization/Annotations_and_Text\|Annotations_and_Text]] |
> > > > > 
> > > 
> > > > [!g-white]- Python Data Visualization - Matplotlib & Seaborn Masterclass
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Python Data Visualization - Matplotlib & Seaborn Masterclass | [[Learning/Programming/Python/Data Visualisation/Python Data Visualization - Matplotlib & Seaborn Masterclass/Untitled\|Untitled]] |
> > > > | Section 1 - Getting Started | [[Learning/Programming/Python/Data Visualisation/Python Data Visualization - Matplotlib & Seaborn Masterclass/Section 1 - Getting Started/1. Course Structure & Outline\|1. Course Structure & Outline]] |
> > > > | Section 2 - Intro to Data Visualisation | [[Learning/Programming/Python/Data Visualisation/Python Data Visualization - Matplotlib & Seaborn Masterclass/Section 2 - Intro to Data Visualisation/10. Chart Formatting & Storytelling\|10. Chart Formatting & Storytelling]] |
> > > > | Section 3 - Matplotlib Fundamentals | [[Learning/Programming/Python/Data Visualisation/Python Data Visualization - Matplotlib & Seaborn Masterclass/Section 3 - Matplotlib Fundamentals/13. Intro to Matplotlib\|13. Intro to Matplotlib]] |
> > > > | Section 4 - PROJECT 1 Analyzing the Global Coffee Market | [[Learning/Programming/Python/Data Visualisation/Python Data Visualization - Matplotlib & Seaborn Masterclass/Section 4 - PROJECT 1 Analyzing the Global Coffee Market/52. Project 1 Introduction\|52. Project 1 Introduction]] |
> > > > | Section 5 - Advanced Customization | [[Learning/Programming/Python/Data Visualisation/Python Data Visualization - Matplotlib & Seaborn Masterclass/Section 5 - Advanced Customization/54. Intro to Advanced Customization\|54. Intro to Advanced Customization]] |
> > > > | Section 6 - PROJECT 2 Visualizing Global Coffee Production | [[Learning/Programming/Python/Data Visualisation/Python Data Visualization - Matplotlib & Seaborn Masterclass/Section 6 - PROJECT 2 Visualizing Global Coffee Production/71. Project 2 Introduction\|71. Project 2 Introduction]] |
> > > > | Section 7 - Visualization with Seaborn | [[Learning/Programming/Python/Data Visualisation/Python Data Visualization - Matplotlib & Seaborn Masterclass/Section 7 - Visualization with Seaborn/73. Intro to Seaborn\|73. Intro to Seaborn]] |
> > > > | Section 8 - PROJECT 3 Analyzing Used Car Sales | [[Learning/Programming/Python/Data Visualisation/Python Data Visualization - Matplotlib & Seaborn Masterclass/Section 8 - PROJECT 3 Analyzing Used Car Sales/92. Project 3 Introduction\|92. Project 3 Introduction]] |
> > > > | Section 9 - BONUS LESSON | [[Learning/Programming/Python/Data Visualisation/Python Data Visualization - Matplotlib & Seaborn Masterclass/Section 9 - BONUS LESSON/94. BONUS LESSON\|94. BONUS LESSON]] |
> > > > 
> > > > > [!g-white]- Section 1 - Getting Started
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 1 - Getting Started | [[Learning/Programming/Python/Data Visualisation/Python Data Visualization - Matplotlib & Seaborn Masterclass/Section 1 - Getting Started/1. Course Structure & Outline\|1. Course Structure & Outline]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 2 - Intro to Data Visualisation
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 2 - Intro to Data Visualisation | [[Learning/Programming/Python/Data Visualisation/Python Data Visualization - Matplotlib & Seaborn Masterclass/Section 2 - Intro to Data Visualisation/10. Chart Formatting & Storytelling\|10. Chart Formatting & Storytelling]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 3 - Matplotlib Fundamentals
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 3 - Matplotlib Fundamentals | [[Learning/Programming/Python/Data Visualisation/Python Data Visualization - Matplotlib & Seaborn Masterclass/Section 3 - Matplotlib Fundamentals/13. Intro to Matplotlib\|13. Intro to Matplotlib]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 4 - PROJECT 1 Analyzing the Global Coffee Market
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 4 - PROJECT 1 Analyzing the Global Coffee Market | [[Learning/Programming/Python/Data Visualisation/Python Data Visualization - Matplotlib & Seaborn Masterclass/Section 4 - PROJECT 1 Analyzing the Global Coffee Market/52. Project 1 Introduction\|52. Project 1 Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 5 - Advanced Customization
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 5 - Advanced Customization | [[Learning/Programming/Python/Data Visualisation/Python Data Visualization - Matplotlib & Seaborn Masterclass/Section 5 - Advanced Customization/54. Intro to Advanced Customization\|54. Intro to Advanced Customization]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 6 - PROJECT 2 Visualizing Global Coffee Production
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 6 - PROJECT 2 Visualizing Global Coffee Production | [[Learning/Programming/Python/Data Visualisation/Python Data Visualization - Matplotlib & Seaborn Masterclass/Section 6 - PROJECT 2 Visualizing Global Coffee Production/71. Project 2 Introduction\|71. Project 2 Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 7 - Visualization with Seaborn
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 7 - Visualization with Seaborn | [[Learning/Programming/Python/Data Visualisation/Python Data Visualization - Matplotlib & Seaborn Masterclass/Section 7 - Visualization with Seaborn/73. Intro to Seaborn\|73. Intro to Seaborn]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 8 - PROJECT 3 Analyzing Used Car Sales
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 8 - PROJECT 3 Analyzing Used Car Sales | [[Learning/Programming/Python/Data Visualisation/Python Data Visualization - Matplotlib & Seaborn Masterclass/Section 8 - PROJECT 3 Analyzing Used Car Sales/92. Project 3 Introduction\|92. Project 3 Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 9 - BONUS LESSON
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 9 - BONUS LESSON | [[Learning/Programming/Python/Data Visualisation/Python Data Visualization - Matplotlib & Seaborn Masterclass/Section 9 - BONUS LESSON/94. BONUS LESSON\|94. BONUS LESSON]] |
> > > > > 
> > 
> > > [!g-white]- Design patterns
> > > 
> > > 
> > > > [!g-white]- Design Patterns in Python
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Design Patterns in Python | [[Learning/Programming/Python/Design patterns/Design Patterns in Python/Design Patterns in Python\|Design Patterns in Python]] |
> > > > | Section 1 - Introduction | [[Learning/Programming/Python/Design patterns/Design Patterns in Python/Section 1 - Introduction/1. Environment Setup\|1. Environment Setup]] |
> > > > | Section 2 - Creational Design Patterns | [[Learning/Programming/Python/Design patterns/Design Patterns in Python/Section 2 - Creational Design Patterns/10. Builder\|10. Builder]] |
> > > > | Section 3 - Structural Design Patterns | [[Learning/Programming/Python/Design patterns/Design Patterns in Python/Section 3 - Structural Design Patterns/19. Decorator\|19. Decorator]] |
> > > > | Section 4 - Behavioural Design Patterns | [[Learning/Programming/Python/Design patterns/Design Patterns in Python/Section 4 - Behavioural Design Patterns/45. Command\|45. Command]] |
> > > > | Section 5 - Summary | [[Learning/Programming/Python/Design patterns/Design Patterns in Python/Section 5 - Summary/78. Summary\|78. Summary]] |
> > > > 
> > > > > [!g-white]- Section 1 - Introduction
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 1 - Introduction | [[Learning/Programming/Python/Design patterns/Design Patterns in Python/Section 1 - Introduction/1. Environment Setup\|1. Environment Setup]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 2 - Creational Design Patterns
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 2 - Creational Design Patterns | [[Learning/Programming/Python/Design patterns/Design Patterns in Python/Section 2 - Creational Design Patterns/10. Builder\|10. Builder]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 3 - Structural Design Patterns
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 3 - Structural Design Patterns | [[Learning/Programming/Python/Design patterns/Design Patterns in Python/Section 3 - Structural Design Patterns/19. Decorator\|19. Decorator]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 4 - Behavioural Design Patterns
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 4 - Behavioural Design Patterns | [[Learning/Programming/Python/Design patterns/Design Patterns in Python/Section 4 - Behavioural Design Patterns/45. Command\|45. Command]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 5 - Summary
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 5 - Summary | [[Learning/Programming/Python/Design patterns/Design Patterns in Python/Section 5 - Summary/78. Summary\|78. Summary]] |
> > > > > 
> > 
> > > [!g-white]- Exploratory Data Analysis
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | Exploratory Data Analysis | [[Learning/Programming/Python/Exploratory Data Analysis/EDA\|EDA]] |
> > > 
> > 
> > > [!g-white]- FastAPI
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | FastAPI | [[Learning/Programming/Python/FastAPI/FastAPI\|FastAPI]] |
> > > | Section 1 - Introduction | [[Learning/Programming/Python/FastAPI/Section 1 - Introduction/1. Introduction\|1. Introduction]] |
> > > | Section 10 - Authentication & Authorization | [[Learning/Programming/Python/FastAPI/Section 10 - Authentication & Authorization/116. FastAPI Project - Starting Authentication & Authorization\|116. FastAPI Project - Starting Authentication & Authorization]] |
> > > | Section 11 - Authenticate Requests | [[Learning/Programming/Python/FastAPI/Section 11 - Authenticate Requests/130. FastAPI Project - Post Todo - User ID\|130. FastAPI Project - Post Todo - User ID]] |
> > > | Section 12 - Large Production Database Setup | [[Learning/Programming/Python/FastAPI/Section 12 - Large Production Database Setup/138. FastAPI Project - Production DBMS\|138. FastAPI Project - Production DBMS]] |
> > > | Section 13 - Project 3.5 - Alembic Data Migration | [[Learning/Programming/Python/FastAPI/Section 13 - Project 3.5 - Alembic Data Migration/149. Alembic Data Migration Overview\|149. Alembic Data Migration Overview]] |
> > > | Section 14 - Project 4 - Unit & Integration Testing | [[Learning/Programming/Python/FastAPI/Section 14 - Project 4 - Unit & Integration Testing/157. Testing Overview\|157. Testing Overview]] |
> > > | Section 15 - Project 5 - Full Stack Application | [[Learning/Programming/Python/FastAPI/Section 15 - Project 5 - Full Stack Application/182. Full Stack Introduction\|182. Full Stack Introduction]] |
> > > | Section 16 - Git - Version Control | [[Learning/Programming/Python/FastAPI/Section 16 - Git - Version Control/198. Git Introduction\|198. Git Introduction]] |
> > > | Section 17 - Deploying FastAPI Applications | [[Learning/Programming/Python/FastAPI/Section 17 - Deploying FastAPI Applications/208. Deployment - Render Introduction\|208. Deployment - Render Introduction]] |
> > > | Section 19 - Summary | [[Learning/Programming/Python/FastAPI/Section 19 - Summary/241. Bonus Lecture\|241. Bonus Lecture]] |
> > > | Section 2 - Python Installation and Refresher | [[Learning/Programming/Python/FastAPI/Section 2 - Python Installation and Refresher/10. Python Setup - Mac\|10. Python Setup - Mac]] |
> > > | Section 3 - FastAPI Overview | [[Learning/Programming/Python/FastAPI/Section 3 - FastAPI Overview/61. FastAPI Overview\|61. FastAPI Overview]] |
> > > | Section 4 - FastAPI Setup & Installation | [[Learning/Programming/Python/FastAPI/Section 4 - FastAPI Setup & Installation/62. Virtual Environments Overview\|62. Virtual Environments Overview]] |
> > > | Section 5 - Project 1 - FastAPI Request Method Logic | [[Learning/Programming/Python/FastAPI/Section 5 - Project 1 - FastAPI Request Method Logic/65. Books Project Introduction\|65. Books Project Introduction]] |
> > > | Section 6 - Project 2 - Move Fast with FastAPI | [[Learning/Programming/Python/FastAPI/Section 6 - Project 2 - Move Fast with FastAPI/100. FastAPI Project - Explicit Status Code Responses\|100. FastAPI Project - Explicit Status Code Responses]] |
> > > | Section 7 - Project 3 - Complete RESTFUL APIs | [[Learning/Programming/Python/FastAPI/Section 7 - Project 3 - Complete RESTFUL APIs/101. Project 3 - Overview\|101. Project 3 - Overview]] |
> > > | Section 8 - Setup Database | [[Learning/Programming/Python/FastAPI/Section 8 - Setup Database/103. FastAPI Project - SQL Database Introduction\|103. FastAPI Project - SQL Database Introduction]] |
> > > | Section 9 - API Request Methods | [[Learning/Programming/Python/FastAPI/Section 9 - API Request Methods/111. FastAPI Project - Get All Todos from Database\|111. FastAPI Project - Get All Todos from Database]] |
> > > 
> > > > [!g-white]- Section 1 - Introduction
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 1 - Introduction | [[Learning/Programming/Python/FastAPI/Section 1 - Introduction/1. Introduction\|1. Introduction]] |
> > > > 
> > > 
> > > > [!g-white]- Section 10 - Authentication & Authorization
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 10 - Authentication & Authorization | [[Learning/Programming/Python/FastAPI/Section 10 - Authentication & Authorization/116. FastAPI Project - Starting Authentication & Authorization\|116. FastAPI Project - Starting Authentication & Authorization]] |
> > > > 
> > > 
> > > > [!g-white]- Section 11 - Authenticate Requests
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 11 - Authenticate Requests | [[Learning/Programming/Python/FastAPI/Section 11 - Authenticate Requests/130. FastAPI Project - Post Todo - User ID\|130. FastAPI Project - Post Todo - User ID]] |
> > > > 
> > > 
> > > > [!g-white]- Section 12 - Large Production Database Setup
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 12 - Large Production Database Setup | [[Learning/Programming/Python/FastAPI/Section 12 - Large Production Database Setup/138. FastAPI Project - Production DBMS\|138. FastAPI Project - Production DBMS]] |
> > > > 
> > > 
> > > > [!g-white]- Section 13 - Project 3.5 - Alembic Data Migration
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 13 - Project 3.5 - Alembic Data Migration | [[Learning/Programming/Python/FastAPI/Section 13 - Project 3.5 - Alembic Data Migration/149. Alembic Data Migration Overview\|149. Alembic Data Migration Overview]] |
> > > > 
> > > 
> > > > [!g-white]- Section 14 - Project 4 - Unit & Integration Testing
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 14 - Project 4 - Unit & Integration Testing | [[Learning/Programming/Python/FastAPI/Section 14 - Project 4 - Unit & Integration Testing/157. Testing Overview\|157. Testing Overview]] |
> > > > 
> > > 
> > > > [!g-white]- Section 15 - Project 5 - Full Stack Application
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 15 - Project 5 - Full Stack Application | [[Learning/Programming/Python/FastAPI/Section 15 - Project 5 - Full Stack Application/182. Full Stack Introduction\|182. Full Stack Introduction]] |
> > > > 
> > > 
> > > > [!g-white]- Section 16 - Git - Version Control
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 16 - Git - Version Control | [[Learning/Programming/Python/FastAPI/Section 16 - Git - Version Control/198. Git Introduction\|198. Git Introduction]] |
> > > > 
> > > 
> > > > [!g-white]- Section 17 - Deploying FastAPI Applications
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 17 - Deploying FastAPI Applications | [[Learning/Programming/Python/FastAPI/Section 17 - Deploying FastAPI Applications/208. Deployment - Render Introduction\|208. Deployment - Render Introduction]] |
> > > > 
> > > 
> > > > [!g-white]- Section 19 - Summary
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 19 - Summary | [[Learning/Programming/Python/FastAPI/Section 19 - Summary/241. Bonus Lecture\|241. Bonus Lecture]] |
> > > > 
> > > 
> > > > [!g-white]- Section 2 - Python Installation and Refresher
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 2 - Python Installation and Refresher | [[Learning/Programming/Python/FastAPI/Section 2 - Python Installation and Refresher/10. Python Setup - Mac\|10. Python Setup - Mac]] |
> > > > 
> > > 
> > > > [!g-white]- Section 3 - FastAPI Overview
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 3 - FastAPI Overview | [[Learning/Programming/Python/FastAPI/Section 3 - FastAPI Overview/61. FastAPI Overview\|61. FastAPI Overview]] |
> > > > 
> > > 
> > > > [!g-white]- Section 4 - FastAPI Setup & Installation
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 4 - FastAPI Setup & Installation | [[Learning/Programming/Python/FastAPI/Section 4 - FastAPI Setup & Installation/62. Virtual Environments Overview\|62. Virtual Environments Overview]] |
> > > > 
> > > 
> > > > [!g-white]- Section 5 - Project 1 - FastAPI Request Method Logic
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 5 - Project 1 - FastAPI Request Method Logic | [[Learning/Programming/Python/FastAPI/Section 5 - Project 1 - FastAPI Request Method Logic/65. Books Project Introduction\|65. Books Project Introduction]] |
> > > > 
> > > 
> > > > [!g-white]- Section 6 - Project 2 - Move Fast with FastAPI
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 6 - Project 2 - Move Fast with FastAPI | [[Learning/Programming/Python/FastAPI/Section 6 - Project 2 - Move Fast with FastAPI/100. FastAPI Project - Explicit Status Code Responses\|100. FastAPI Project - Explicit Status Code Responses]] |
> > > > 
> > > 
> > > > [!g-white]- Section 7 - Project 3 - Complete RESTFUL APIs
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 7 - Project 3 - Complete RESTFUL APIs | [[Learning/Programming/Python/FastAPI/Section 7 - Project 3 - Complete RESTFUL APIs/101. Project 3 - Overview\|101. Project 3 - Overview]] |
> > > > 
> > > 
> > > > [!g-white]- Section 8 - Setup Database
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 8 - Setup Database | [[Learning/Programming/Python/FastAPI/Section 8 - Setup Database/103. FastAPI Project - SQL Database Introduction\|103. FastAPI Project - SQL Database Introduction]] |
> > > > 
> > > 
> > > > [!g-white]- Section 9 - API Request Methods
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 9 - API Request Methods | [[Learning/Programming/Python/FastAPI/Section 9 - API Request Methods/111. FastAPI Project - Get All Todos from Database\|111. FastAPI Project - Get All Todos from Database]] |
> > > > 
> > 
> > > [!g-white]- MathByte Academy
> > > 
> > > 
> > > > [!g-white]- Extra info
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Extra info | [[Learning/Programming/Python/MathByte Academy/Extra info/Extra info\|Extra info]] |
> > > > | A Deep Dive into Python's Dataclasses | [[Learning/Programming/Python/MathByte Academy/Extra info/A Deep Dive into Python's Dataclasses/A Deep Dive into Python's Dataclasses (Part 1)\|A Deep Dive into Python's Dataclasses (Part 1)]] |
> > > > | context_with_gil_and_threads(Optional) | [[Learning/Programming/Python/MathByte Academy/Extra info/context_with_gil_and_threads(Optional)/01_gil_basics — What is the GIL and why it exists\|01_gil_basics — What is the GIL and why it exists]] |
> > > > | multiple_inheritance | [[Learning/Programming/Python/MathByte Academy/Extra info/multiple_inheritance/01_multiple_inheritance_intro — Basic syntax and structure\|01_multiple_inheritance_intro — Basic syntax and structure]] |
> > > > | Python Design Patterns | [[Learning/Programming/Python/MathByte Academy/Extra info/Python Design Patterns/Python Design Patterns\|Python Design Patterns]] |
> > > > | Python Logging Demystified | [[Learning/Programming/Python/MathByte Academy/Extra info/Python Logging Demystified/Python Logging Demystified - Part 1 - Concepts\|Python Logging Demystified - Part 1 - Concepts]] |
> > > > | super() | [[Learning/Programming/Python/MathByte Academy/Extra info/super()/01_super_basics — Using super() in single inheritance\|01_super_basics — Using super() in single inheritance]] |
> > > > 
> > > > > [!g-white]- A Deep Dive into Python's Dataclasses
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | A Deep Dive into Python's Dataclasses | [[Learning/Programming/Python/MathByte Academy/Extra info/A Deep Dive into Python's Dataclasses/A Deep Dive into Python's Dataclasses (Part 1)\|A Deep Dive into Python's Dataclasses (Part 1)]] |
> > > > > 
> > > > 
> > > > > [!g-white]- context_with_gil_and_threads(Optional)
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | context_with_gil_and_threads(Optional) | [[Learning/Programming/Python/MathByte Academy/Extra info/context_with_gil_and_threads(Optional)/01_gil_basics — What is the GIL and why it exists\|01_gil_basics — What is the GIL and why it exists]] |
> > > > > 
> > > > 
> > > > > [!g-white]- multiple_inheritance
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | multiple_inheritance | [[Learning/Programming/Python/MathByte Academy/Extra info/multiple_inheritance/01_multiple_inheritance_intro — Basic syntax and structure\|01_multiple_inheritance_intro — Basic syntax and structure]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Python Design Patterns
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Python Design Patterns | [[Learning/Programming/Python/MathByte Academy/Extra info/Python Design Patterns/Python Design Patterns\|Python Design Patterns]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Python Logging Demystified
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Python Logging Demystified | [[Learning/Programming/Python/MathByte Academy/Extra info/Python Logging Demystified/Python Logging Demystified - Part 1 - Concepts\|Python Logging Demystified - Part 1 - Concepts]] |
> > > > > 
> > > > 
> > > > > [!g-white]- super()
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | super() | [[Learning/Programming/Python/MathByte Academy/Extra info/super()/01_super_basics — Using super() in single inheritance\|01_super_basics — Using super() in single inheritance]] |
> > > > > 
> > > 
> > > > [!g-white]- Python 3 Deep Dive
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Python 3 Deep Dive | [[Learning/Programming/Python/MathByte Academy/Python 3 Deep Dive/Python 3 Deep Dive\|Python 3 Deep Dive]] |
> > > > | Pydantic V2 - Essentials | [[Learning/Programming/Python/MathByte Academy/Python 3 Deep Dive/Pydantic V2 - Essentials/Pydantic V2 - Essentials\|Pydantic V2 - Essentials]] |
> > > > | Python 3 Deep Dive (Part 1 - Functional) | [[Learning/Programming/Python/MathByte Academy/Python 3 Deep Dive/Python 3 Deep Dive (Part 1 - Functional)/Python 3 Deep Dive (Part 1 - Functional)\|Python 3 Deep Dive (Part 1 - Functional)]] |
> > > > | Python 3 Deep Dive (Part 4 - OOP) | [[Learning/Programming/Python/MathByte Academy/Python 3 Deep Dive/Python 3 Deep Dive (Part 4 - OOP)/Python 3 Deep Dive (Part 4 - OOP)\|Python 3 Deep Dive (Part 4 - OOP)]] |
> > > > 
> > > > > [!g-white]- Pydantic V2 - Essentials
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Pydantic V2 - Essentials | [[Learning/Programming/Python/MathByte Academy/Python 3 Deep Dive/Pydantic V2 - Essentials/Pydantic V2 - Essentials\|Pydantic V2 - Essentials]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Python 3 Deep Dive (Part 1 - Functional)
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Python 3 Deep Dive (Part 1 - Functional) | [[Learning/Programming/Python/MathByte Academy/Python 3 Deep Dive/Python 3 Deep Dive (Part 1 - Functional)/Python 3 Deep Dive (Part 1 - Functional)\|Python 3 Deep Dive (Part 1 - Functional)]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Python 3 Deep Dive (Part 2 - Iterators, Generators)
> > > > > 
> > > > > 
> > > > 
> > > > > [!g-white]- Python 3 Deep Dive (Part 3 - Dictionaries, Sets, JSON)
> > > > > 
> > > > > 
> > > > 
> > > > > [!g-white]- Python 3 Deep Dive (Part 4 - OOP)
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Python 3 Deep Dive (Part 4 - OOP) | [[Learning/Programming/Python/MathByte Academy/Python 3 Deep Dive/Python 3 Deep Dive (Part 4 - OOP)/Python 3 Deep Dive (Part 4 - OOP)\|Python 3 Deep Dive (Part 4 - OOP)]] |
> > > > > 
> > 
> > > [!g-white]- MCP
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | MCP | [[Learning/Programming/Python/MCP/1-introduction-and-context\|1-introduction-and-context]] |
> > > | coursera - introduction-to-model-context-protocol | [[Learning/Programming/Python/MCP/coursera - introduction-to-model-context-protocol/mnemonics\|mnemonics]] |
> > > | coursera-model-context-protocol-advanced-topics | [[Learning/Programming/Python/MCP/coursera-model-context-protocol-advanced-topics/03_assessment-and-next-steps/quiz\|quiz]] |
> > > | Extra info | [[Learning/Programming/Python/MCP/Extra info/Code used\|Code used]] |
> > > | Udemy - MCP Crash Course  Complete Model Context Protocol in a Day | [[Learning/Programming/Python/MCP/Udemy - MCP Crash Course  Complete Model Context Protocol in a Day/Section 1 - Welcome & Course Overview/1. Course Objectives\|1. Course Objectives]] |
> > > 
> > > > [!g-white]- coursera - introduction-to-model-context-protocol
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | coursera - introduction-to-model-context-protocol | [[Learning/Programming/Python/MCP/coursera - introduction-to-model-context-protocol/mnemonics\|mnemonics]] |
> > > > 
> > > > > [!g-white]- 01_introduction
> > > > > 
> > > > > 
> > > > 
> > > > > [!g-white]- 02_hands-on-with-mcp-servers
> > > > > 
> > > > > 
> > > > 
> > > > > [!g-white]- 03_connecting-with-mcp-clients
> > > > > 
> > > > > 
> > > > 
> > > > > [!g-white]- 04_assessment-and-wrap-up
> > > > > 
> > > > > 
> > > 
> > > > [!g-white]- coursera-model-context-protocol-advanced-topics
> > > > 
> > > > 
> > > > > [!g-white]- 01_core-mcp-features
> > > > > 
> > > > > 
> > > > 
> > > > > [!g-white]- 02_transports-and-communication
> > > > > 
> > > > > 
> > > > 
> > > > > [!g-white]- 03_assessment-and-next-steps
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | 03_assessment-and-next-steps | [[Learning/Programming/Python/MCP/coursera-model-context-protocol-advanced-topics/03_assessment-and-next-steps/quiz\|quiz]] |
> > > > > 
> > > 
> > > > [!g-white]- Extra info
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Extra info | [[Learning/Programming/Python/MCP/Extra info/Code used\|Code used]] |
> > > > 
> > > 
> > > > [!g-white]- Udemy - MCP Crash Course  Complete Model Context Protocol in a Day
> > > > 
> > > > 
> > > > > [!g-white]- Section 1 - Welcome & Course Overview
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 1 - Welcome & Course Overview | [[Learning/Programming/Python/MCP/Udemy - MCP Crash Course  Complete Model Context Protocol in a Day/Section 1 - Welcome & Course Overview/1. Course Objectives\|1. Course Objectives]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 10 - MCP Interview
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 10 - MCP Interview | [[Learning/Programming/Python/MCP/Udemy - MCP Crash Course  Complete Model Context Protocol in a Day/Section 10 - MCP Interview/Role Play 1 - MCP Interview\|Role Play 1 - MCP Interview]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 11 - Agent 2 Agent
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 11 - Agent 2 Agent | [[Learning/Programming/Python/MCP/Udemy - MCP Crash Course  Complete Model Context Protocol in a Day/Section 11 - Agent 2 Agent/71. Introduction to A2A - Agent to Agent Protocol\|71. Introduction to A2A - Agent to Agent Protocol]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 12 - FastMCP 2.0 featuring Jeremaiah Lowin
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 12 - FastMCP 2.0 featuring Jeremaiah Lowin | [[Learning/Programming/Python/MCP/Udemy - MCP Crash Course  Complete Model Context Protocol in a Day/Section 12 - FastMCP 2.0 featuring Jeremaiah Lowin/72. How FastMCP Began- Jeremiah's Journey and the Need for Better MCP Tools\|72. How FastMCP Began- Jeremiah's Journey and the Need for Better MCP Tools]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 13 - Advanced Topics In MCP
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 13 - Advanced Topics In MCP | [[Learning/Programming/Python/MCP/Udemy - MCP Crash Course  Complete Model Context Protocol in a Day/Section 13 - Advanced Topics In MCP/77. Theory Sampling\|77. Theory Sampling]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 14 - Whats Wrong with MCP
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 14 - Whats Wrong with MCP | [[Learning/Programming/Python/MCP/Udemy - MCP Crash Course  Complete Model Context Protocol in a Day/Section 14 - Whats Wrong with MCP/80. The 4 Major Drawbacks of the Model Context Protocol\|80. The 4 Major Drawbacks of the Model Context Protocol]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 15 - Agent Skills
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 15 - Agent Skills | [[Learning/Programming/Python/MCP/Udemy - MCP Crash Course  Complete Model Context Protocol in a Day/Section 15 - Agent Skills/82. Intro\|82. Intro]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 16 - Bonus
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 16 - Bonus | [[Learning/Programming/Python/MCP/Udemy - MCP Crash Course  Complete Model Context Protocol in a Day/Section 16 - Bonus/86. Bonus\|86. Bonus]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 2 - Hello World MCP - Configuring Pre Built MCP Servers with Weather Server
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 2 - Hello World MCP - Configuring Pre Built MCP Servers with Weather Server | [[Learning/Programming/Python/MCP/Udemy - MCP Crash Course  Complete Model Context Protocol in a Day/Section 2 - Hello World MCP - Configuring Pre Built MCP Servers with Weather Server/10. Configure Claude Desktop with a local MCP Server\|10. Configure Claude Desktop with a local MCP Server]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 3 - Model Context Protocol Architecture
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 3 - Model Context Protocol Architecture | [[Learning/Programming/Python/MCP/Udemy - MCP Crash Course  Complete Model Context Protocol in a Day/Section 3 - Model Context Protocol Architecture/15. MCP Architecture Concepts - Hosts, Servers, Clients, and the Protocol\|15. MCP Architecture Concepts - Hosts, Servers, Clients, and the Protocol]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 4 - MCP Servers
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 4 - MCP Servers | [[Learning/Programming/Python/MCP/Udemy - MCP Crash Course  Complete Model Context Protocol in a Day/Section 4 - MCP Servers/18. The Theory of MCP Servers\|18. The Theory of MCP Servers]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 5 - Building, Securing, and Containerizing an MCP Server
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 5 - Building, Securing, and Containerizing an MCP Server | [[Learning/Programming/Python/MCP/Udemy - MCP Crash Course  Complete Model Context Protocol in a Day/Section 5 - Building, Securing, and Containerizing an MCP Server/22. What are we building\|22. What are we building]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 6 - Connecting LLM Clients - Tool Calling Mechanisms and MCP
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 6 - Connecting LLM Clients - Tool Calling Mechanisms and MCP | [[Learning/Programming/Python/MCP/Udemy - MCP Crash Course  Complete Model Context Protocol in a Day/Section 6 - Connecting LLM Clients - Tool Calling Mechanisms and MCP/32. Intro\|32. Intro]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 7 - Prompts and Reources
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 7 - Prompts and Reources | [[Learning/Programming/Python/MCP/Udemy - MCP Crash Course  Complete Model Context Protocol in a Day/Section 7 - Prompts and Reources/42. MCP Prompts and Resources High Level\|42. MCP Prompts and Resources High Level]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 8 - I LOVE SSE Servers
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 8 - I LOVE SSE Servers | [[Learning/Programming/Python/MCP/Udemy - MCP Crash Course  Complete Model Context Protocol in a Day/Section 8 - I LOVE SSE Servers/50. intro\|50. intro]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 9 - Secure, Cloud native MCP Servers- Auth0 + Cloudflare Workers
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 9 - Secure, Cloud native MCP Servers- Auth0 + Cloudflare Workers | [[Learning/Programming/Python/MCP/Udemy - MCP Crash Course  Complete Model Context Protocol in a Day/Section 9 - Secure, Cloud native MCP Servers- Auth0 + Cloudflare Workers/55. Introduction- How to Bridge Local AI Apps and Secure Cloud APIs with MCP Servers\|55. Introduction- How to Bridge Local AI Apps and Secure Cloud APIs with MCP Servers]] |
> > > > > 
> > 
> > > [!g-white]- Numpy
> > > 
> > > 
> > > > [!g-white]- Preprocessing Data with NumPy
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Preprocessing Data with NumPy | [[Learning/Programming/Python/Numpy/Preprocessing Data with NumPy/Untitled\|Untitled]] |
> > > > | Section 1 - Introduction to NumPy | [[Learning/Programming/Python/Numpy/Preprocessing Data with NumPy/Section 1 - Introduction to NumPy/1. What Does the Course Cover MOC\|1. What Does the Course Cover MOC]] |
> > > > | Section 2 - Why Do We Use NumPy | [[Learning/Programming/Python/Numpy/Preprocessing Data with NumPy/Section 2 - Why Do We Use NumPy/10. ndarrays\|10. ndarrays]] |
> > > > | Section 3 - NumPy Fundamentals | [[Learning/Programming/Python/Numpy/Preprocessing Data with NumPy/Section 3 - NumPy Fundamentals/13. Indexing\|13. Indexing]] |
> > > > | Section 4 - Working with Arrays | [[Learning/Programming/Python/Numpy/Preprocessing Data with NumPy/Section 4 - Working with Arrays/20. Basic Slicing\|20. Basic Slicing]] |
> > > > | Section 5 - Generating Data with NumPy | [[Learning/Programming/Python/Numpy/Preprocessing Data with NumPy/Section 5 - Generating Data with NumPy/25. Empty Arrays, Arrays of Identical Values\|25. Empty Arrays, Arrays of Identical Values]] |
> > > > | Section 6 - Importing and Saving Data | [[Learning/Programming/Python/Numpy/Preprocessing Data with NumPy/Section 6 - Importing and Saving Data/33. Importing Data with Numpy - np.loadtxt() vs np.genfromtxt()\|33. Importing Data with Numpy - np.loadtxt() vs np.genfromtxt()]] |
> > > > | Section 7 - Statistics with NumPy | [[Learning/Programming/Python/Numpy/Preprocessing Data with NumPy/Section 7 - Statistics with NumPy/41. Using NumPy Statistical Functions\|41. Using NumPy Statistical Functions]] |
> > > > | Section 8 - Manipulating Data with NumPy | [[Learning/Programming/Python/Numpy/Preprocessing Data with NumPy/Section 8 - Manipulating Data with NumPy/50. Checking for Missing Values\|50. Checking for Missing Values]] |
> > > > | Section 9 - A NumPy Practical Example | [[Learning/Programming/Python/Numpy/Preprocessing Data with NumPy/Section 9 - A NumPy Practical Example/63. Setting Up - Introduction to the Practical Example\|63. Setting Up - Introduction to the Practical Example]] |
> > > > 
> > > > > [!g-white]- Section 1 - Introduction to NumPy
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 1 - Introduction to NumPy | [[Learning/Programming/Python/Numpy/Preprocessing Data with NumPy/Section 1 - Introduction to NumPy/1. What Does the Course Cover MOC\|1. What Does the Course Cover MOC]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 2 - Why Do We Use NumPy
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 2 - Why Do We Use NumPy | [[Learning/Programming/Python/Numpy/Preprocessing Data with NumPy/Section 2 - Why Do We Use NumPy/10. ndarrays\|10. ndarrays]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 3 - NumPy Fundamentals
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 3 - NumPy Fundamentals | [[Learning/Programming/Python/Numpy/Preprocessing Data with NumPy/Section 3 - NumPy Fundamentals/13. Indexing\|13. Indexing]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 4 - Working with Arrays
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 4 - Working with Arrays | [[Learning/Programming/Python/Numpy/Preprocessing Data with NumPy/Section 4 - Working with Arrays/20. Basic Slicing\|20. Basic Slicing]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 5 - Generating Data with NumPy
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 5 - Generating Data with NumPy | [[Learning/Programming/Python/Numpy/Preprocessing Data with NumPy/Section 5 - Generating Data with NumPy/25. Empty Arrays, Arrays of Identical Values\|25. Empty Arrays, Arrays of Identical Values]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 6 - Importing and Saving Data
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 6 - Importing and Saving Data | [[Learning/Programming/Python/Numpy/Preprocessing Data with NumPy/Section 6 - Importing and Saving Data/33. Importing Data with Numpy - np.loadtxt() vs np.genfromtxt()\|33. Importing Data with Numpy - np.loadtxt() vs np.genfromtxt()]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 7 - Statistics with NumPy
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 7 - Statistics with NumPy | [[Learning/Programming/Python/Numpy/Preprocessing Data with NumPy/Section 7 - Statistics with NumPy/41. Using NumPy Statistical Functions\|41. Using NumPy Statistical Functions]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 8 - Manipulating Data with NumPy
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 8 - Manipulating Data with NumPy | [[Learning/Programming/Python/Numpy/Preprocessing Data with NumPy/Section 8 - Manipulating Data with NumPy/50. Checking for Missing Values\|50. Checking for Missing Values]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 9 - A NumPy Practical Example
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 9 - A NumPy Practical Example | [[Learning/Programming/Python/Numpy/Preprocessing Data with NumPy/Section 9 - A NumPy Practical Example/63. Setting Up - Introduction to the Practical Example\|63. Setting Up - Introduction to the Practical Example]] |
> > > > > 
> > > 
> > > > [!g-white]- Udemy - Intro to NumPy
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Udemy - Intro to NumPy | [[Learning/Programming/Python/Numpy/Udemy - Intro to NumPy/1. Overview\|1. Overview]] |
> > > > 
> > 
> > > [!g-white]- Pandas
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | Pandas | [[Learning/Programming/Python/Pandas/Pandas\|Pandas]] |
> > > | Data Representation files | [[Learning/Programming/Python/Pandas/Data Representation files/customers.head()\|customers.head()]] |
> > > | Extrainfo | [[Learning/Programming/Python/Pandas/Extrainfo/0000Extra info\|0000Extra info]] |
> > > | Section 1 - Installation and Setup | [[Learning/Programming/Python/Pandas/Section 1 - Installation and Setup/1. Introduction to the Course\|1. Introduction to the Course]] |
> > > | Section 10 - Merging, Joining, and Concatenating DataFrames | [[Learning/Programming/Python/Pandas/Section 10 - Merging, Joining, and Concatenating DataFrames/107. Intro to the Merging DataFrames Module\|107. Intro to the Merging DataFrames Module]] |
> > > | Section 11 - Working with Dates and Times in Datasets | [[Learning/Programming/Python/Pandas/Section 11 - Working with Dates and Times in Datasets/117. Intro to the Working with Dates and Times Module and Review of Python's datetime\|117. Intro to the Working with Dates and Times Module and Review of Python's datetime]] |
> > > | Section 12 - Input and Output in pandas | [[Learning/Programming/Python/Pandas/Section 12 - Input and Output in pandas/125. URL for Next Lesson's Dataset\|125. URL for Next Lesson's Dataset]] |
> > > | Section 13 - Visualization | [[Learning/Programming/Python/Pandas/Section 13 - Visualization/131. Install matplotlib Library for Visualization\|131. Install matplotlib Library for Visualization]] |
> > > | Section 14 - Options and Settings in pandas | [[Learning/Programming/Python/Pandas/Section 14 - Options and Settings in pandas/202. Introduction to the Options and Settings Module\|202. Introduction to the Options and Settings Module]] |
> > > | Section 2 - Python Crash Course | [[Learning/Programming/Python/Pandas/Section 2 - Python Crash Course/Section 2 - Python Crash Course\|Section 2 - Python Crash Course]] |
> > > | Section 3 - Series | [[Learning/Programming/Python/Pandas/Section 3 - Series/23. Create a Series Object from a List\|23. Create a Series Object from a List]] |
> > > | Section 4 - DataFrames I Introduction | [[Learning/Programming/Python/Pandas/Section 4 - DataFrames I Introduction/44. Methods and Attributes between Series and DataFrames\|44. Methods and Attributes between Series and DataFrames]] |
> > > | Section 5 - DataFrames II Filtering Data | [[Learning/Programming/Python/Pandas/Section 5 - DataFrames II Filtering Data/100. Coding Exercise Solution - Filter DataFrame with More than One Condition (OR)\|100. Coding Exercise Solution - Filter DataFrame with More than One Condition (OR)]] |
> > > | Section 6 - DataFrames III Data Extraction | [[Learning/Programming/Python/Pandas/Section 6 - DataFrames III Data Extraction/68. This Module's Dataset\|68. This Module's Dataset]] |
> > > | Section 7 - Working with Text Data | [[Learning/Programming/Python/Pandas/Section 7 - Working with Text Data/81. This Module's Dataset\|81. This Module's Dataset]] |
> > > | Section 8 - MultiIndex | [[Learning/Programming/Python/Pandas/Section 8 - MultiIndex/88. Intro to the MultiIndex Module\|88. Intro to the MultiIndex Module]] |
> > > | Section 9 - The GroupBy Object | [[Learning/Programming/Python/Pandas/Section 9 - The GroupBy Object/100. Intro to the GroupBy Module\|100. Intro to the GroupBy Module]] |
> > > 
> > > > [!g-white]- Data Representation files
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Data Representation files | [[Learning/Programming/Python/Pandas/Data Representation files/customers.head()\|customers.head()]] |
> > > > 
> > > 
> > > > [!g-white]- Extrainfo
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Extrainfo | [[Learning/Programming/Python/Pandas/Extrainfo/0000Extra info\|0000Extra info]] |
> > > > 
> > > 
> > > > [!g-white]- Section 1 - Installation and Setup
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 1 - Installation and Setup | [[Learning/Programming/Python/Pandas/Section 1 - Installation and Setup/1. Introduction to the Course\|1. Introduction to the Course]] |
> > > > 
> > > 
> > > > [!g-white]- Section 10 - Merging, Joining, and Concatenating DataFrames
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 10 - Merging, Joining, and Concatenating DataFrames | [[Learning/Programming/Python/Pandas/Section 10 - Merging, Joining, and Concatenating DataFrames/107. Intro to the Merging DataFrames Module\|107. Intro to the Merging DataFrames Module]] |
> > > > 
> > > 
> > > > [!g-white]- Section 11 - Working with Dates and Times in Datasets
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 11 - Working with Dates and Times in Datasets | [[Learning/Programming/Python/Pandas/Section 11 - Working with Dates and Times in Datasets/117. Intro to the Working with Dates and Times Module and Review of Python's datetime\|117. Intro to the Working with Dates and Times Module and Review of Python's datetime]] |
> > > > 
> > > 
> > > > [!g-white]- Section 12 - Input and Output in pandas
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 12 - Input and Output in pandas | [[Learning/Programming/Python/Pandas/Section 12 - Input and Output in pandas/125. URL for Next Lesson's Dataset\|125. URL for Next Lesson's Dataset]] |
> > > > 
> > > 
> > > > [!g-white]- Section 13 - Visualization
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 13 - Visualization | [[Learning/Programming/Python/Pandas/Section 13 - Visualization/131. Install matplotlib Library for Visualization\|131. Install matplotlib Library for Visualization]] |
> > > > 
> > > 
> > > > [!g-white]- Section 14 - Options and Settings in pandas
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 14 - Options and Settings in pandas | [[Learning/Programming/Python/Pandas/Section 14 - Options and Settings in pandas/202. Introduction to the Options and Settings Module\|202. Introduction to the Options and Settings Module]] |
> > > > 
> > > 
> > > > [!g-white]- Section 2 - Python Crash Course
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 2 - Python Crash Course | [[Learning/Programming/Python/Pandas/Section 2 - Python Crash Course/Section 2 - Python Crash Course\|Section 2 - Python Crash Course]] |
> > > > 
> > > 
> > > > [!g-white]- Section 3 - Series
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 3 - Series | [[Learning/Programming/Python/Pandas/Section 3 - Series/23. Create a Series Object from a List\|23. Create a Series Object from a List]] |
> > > > 
> > > 
> > > > [!g-white]- Section 4 - DataFrames I Introduction
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 4 - DataFrames I Introduction | [[Learning/Programming/Python/Pandas/Section 4 - DataFrames I Introduction/44. Methods and Attributes between Series and DataFrames\|44. Methods and Attributes between Series and DataFrames]] |
> > > > 
> > > 
> > > > [!g-white]- Section 5 - DataFrames II Filtering Data
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 5 - DataFrames II Filtering Data | [[Learning/Programming/Python/Pandas/Section 5 - DataFrames II Filtering Data/100. Coding Exercise Solution - Filter DataFrame with More than One Condition (OR)\|100. Coding Exercise Solution - Filter DataFrame with More than One Condition (OR)]] |
> > > > 
> > > 
> > > > [!g-white]- Section 6 - DataFrames III Data Extraction
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 6 - DataFrames III Data Extraction | [[Learning/Programming/Python/Pandas/Section 6 - DataFrames III Data Extraction/68. This Module's Dataset\|68. This Module's Dataset]] |
> > > > 
> > > 
> > > > [!g-white]- Section 7 - Working with Text Data
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 7 - Working with Text Data | [[Learning/Programming/Python/Pandas/Section 7 - Working with Text Data/81. This Module's Dataset\|81. This Module's Dataset]] |
> > > > 
> > > 
> > > > [!g-white]- Section 8 - MultiIndex
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 8 - MultiIndex | [[Learning/Programming/Python/Pandas/Section 8 - MultiIndex/88. Intro to the MultiIndex Module\|88. Intro to the MultiIndex Module]] |
> > > > 
> > > 
> > > > [!g-white]- Section 9 - The GroupBy Object
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 9 - The GroupBy Object | [[Learning/Programming/Python/Pandas/Section 9 - The GroupBy Object/100. Intro to the GroupBy Module\|100. Intro to the GroupBy Module]] |
> > > > 
> > 
> > > [!g-white]- Plotly_Dash
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | Plotly_Dash | [[Learning/Programming/Python/Plotly_Dash/1. Course Overview\|1. Course Overview]] |
> > > 
> > 
> > > [!g-white]- Practice
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | Practice | [[Learning/Programming/Python/Practice/Practice\|Practice]] |
> > > | Interview questions | [[Learning/Programming/Python/Practice/Interview questions/!r and !s\|!r and !s]] |
> > > | Practice questions | [[Learning/Programming/Python/Practice/Practice questions/1. re, os.scandir, Path, sets, exceptions\|1. re, os.scandir, Path, sets, exceptions]] |
> > > | udemy | [[Learning/Programming/Python/Practice/udemy/210+ Exercises - Python Standard Libraries/210+ Exercises - Python Standard Libraries\|210+ Exercises - Python Standard Libraries]] |
> > > 
> > > > [!g-white]- Interview questions
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Interview questions | [[Learning/Programming/Python/Practice/Interview questions/!r and !s\|!r and !s]] |
> > > > | BOA | [[Learning/Programming/Python/Practice/Interview questions/BOA/CE questions\|CE questions]] |
> > > > | practice problems | [[Learning/Programming/Python/Practice/Interview questions/practice problems/Instance Methods, Class Methods, Static Methods and Alternative Constructors practice\|Instance Methods, Class Methods, Static Methods and Alternative Constructors practice]] |
> > > > 
> > > > > [!g-white]- BOA
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | BOA | [[Learning/Programming/Python/Practice/Interview questions/BOA/CE questions\|CE questions]] |
> > > > > 
> > > > 
> > > > > [!g-white]- practice problems
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | practice problems | [[Learning/Programming/Python/Practice/Interview questions/practice problems/Instance Methods, Class Methods, Static Methods and Alternative Constructors practice\|Instance Methods, Class Methods, Static Methods and Alternative Constructors practice]] |
> > > > > 
> > > 
> > > > [!g-white]- Practice questions
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Practice questions | [[Learning/Programming/Python/Practice/Practice questions/1. re, os.scandir, Path, sets, exceptions\|1. re, os.scandir, Path, sets, exceptions]] |
> > > > | Design Patterns | [[Learning/Programming/Python/Practice/Practice questions/Design Patterns/Abstract factory pattern\|Abstract factory pattern]] |
> > > > | My custom packages | [[Learning/Programming/Python/Practice/Practice questions/My custom packages/abstract class\|abstract class]] |
> > > > 
> > > > > [!g-white]- Design Patterns
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Design Patterns | [[Learning/Programming/Python/Practice/Practice questions/Design Patterns/Abstract factory pattern\|Abstract factory pattern]] |
> > > > > 
> > > > 
> > > > > [!g-white]- My custom packages
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | My custom packages | [[Learning/Programming/Python/Practice/Practice questions/My custom packages/abstract class\|abstract class]] |
> > > > > 
> > > 
> > > > [!g-white]- udemy
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | udemy | [[Learning/Programming/Python/Practice/udemy/Youtube links\|Youtube links]] |
> > > > | 210+ Exercises - Python Standard Libraries | [[Learning/Programming/Python/Practice/udemy/210+ Exercises - Python Standard Libraries/210+ Exercises - Python Standard Libraries\|210+ Exercises - Python Standard Libraries]] |
> > > > | 380+ Exercises - Python Programming Mega Pack - Built-in | [[Learning/Programming/Python/Practice/udemy/380+ Exercises - Python Programming Mega Pack - Built-in/380+ Exercises - Python Programming Mega Pack - Built-in\|380+ Exercises - Python Programming Mega Pack - Built-in]] |
> > > > | Master Python by Coding 100 Practical Problems | [[Learning/Programming/Python/Practice/udemy/Master Python by Coding 100 Practical Problems/Master Python by Coding 100 Practical Problems\|Master Python by Coding 100 Practical Problems]] |
> > > > | Modern Python Application Development in Practice! | [[Learning/Programming/Python/Practice/udemy/Modern Python Application Development in Practice!/Modern Python Application Development in Practice!\|Modern Python Application Development in Practice!]] |
> > > > | PCPP1 - Become Certified Professional in Python Programming 1 | [[Learning/Programming/Python/Practice/udemy/PCPP1 - Become Certified Professional in Python Programming 1/PCPP1 - Become Certified Professional in Python Programming 1\|PCPP1 - Become Certified Professional in Python Programming 1]] |
> > > > | Python 3 Standard Library Essentials | [[Learning/Programming/Python/Practice/udemy/Python 3 Standard Library Essentials/Python 3 Standard Library Essentials\|Python 3 Standard Library Essentials]] |
> > > > | Python Best Parts - Standard Library (Beginner to Advanced) | [[Learning/Programming/Python/Practice/udemy/Python Best Parts - Standard Library (Beginner to Advanced)/Python Best Parts - Standard Library (Beginner to Advanced)\|Python Best Parts - Standard Library (Beginner to Advanced)]] |
> > > > | Python Certification Exam PCAP-31-03 Practice Tests [2024] | [[Learning/Programming/Python/Practice/udemy/Python Certification Exam PCAP-31-03 Practice Tests [2024]/Python Certification Exam PCAP-31-03 Practice Tests [2024]\|Python Certification Exam PCAP-31-03 Practice Tests [2024]]] |
> > > > | Python Certification Exam PCEP-30-02 - Preparation (2025) | [[Learning/Programming/Python/Practice/udemy/Python Certification Exam PCEP-30-02 - Preparation (2025)/Python Certification Exam PCEP-30-02 - Preparation (2025)\|Python Certification Exam PCEP-30-02 - Preparation (2025)]] |
> > > > | Python Exercises for Beginners - Solve 100+ Coding Challenges | [[Learning/Programming/Python/Practice/udemy/Python Exercises for Beginners - Solve 100+ Coding Challenges/Python Exercises for Beginners - Solve 100+ Coding Challenges\|Python Exercises for Beginners - Solve 100+ Coding Challenges]] |
> > > > | Python Programming - 200+ Exercises for Practice | [[Learning/Programming/Python/Practice/udemy/Python Programming - 200+ Exercises for Practice/Python Programming - 200+ Exercises for Practice\|Python Programming - 200+ Exercises for Practice]] |
> > > > 
> > > > > [!g-white]- 210+ Exercises - Python Standard Libraries
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | 210+ Exercises - Python Standard Libraries | [[Learning/Programming/Python/Practice/udemy/210+ Exercises - Python Standard Libraries/210+ Exercises - Python Standard Libraries\|210+ Exercises - Python Standard Libraries]] |
> > > > > 
> > > > 
> > > > > [!g-white]- 380+ Exercises - Python Programming Mega Pack - Built-in
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | 380+ Exercises - Python Programming Mega Pack - Built-in | [[Learning/Programming/Python/Practice/udemy/380+ Exercises - Python Programming Mega Pack - Built-in/380+ Exercises - Python Programming Mega Pack - Built-in\|380+ Exercises - Python Programming Mega Pack - Built-in]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Master Python by Coding 100 Practical Problems
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Master Python by Coding 100 Practical Problems | [[Learning/Programming/Python/Practice/udemy/Master Python by Coding 100 Practical Problems/Master Python by Coding 100 Practical Problems\|Master Python by Coding 100 Practical Problems]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Modern Python Application Development in Practice!
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Modern Python Application Development in Practice! | [[Learning/Programming/Python/Practice/udemy/Modern Python Application Development in Practice!/Modern Python Application Development in Practice!\|Modern Python Application Development in Practice!]] |
> > > > > 
> > > > 
> > > > > [!g-white]- PCPP1 - Become Certified Professional in Python Programming 1
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | PCPP1 - Become Certified Professional in Python Programming 1 | [[Learning/Programming/Python/Practice/udemy/PCPP1 - Become Certified Professional in Python Programming 1/PCPP1 - Become Certified Professional in Python Programming 1\|PCPP1 - Become Certified Professional in Python Programming 1]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Python 3 Standard Library Essentials
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Python 3 Standard Library Essentials | [[Learning/Programming/Python/Practice/udemy/Python 3 Standard Library Essentials/Python 3 Standard Library Essentials\|Python 3 Standard Library Essentials]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Python Best Parts - Standard Library (Beginner to Advanced)
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Python Best Parts - Standard Library (Beginner to Advanced) | [[Learning/Programming/Python/Practice/udemy/Python Best Parts - Standard Library (Beginner to Advanced)/Python Best Parts - Standard Library (Beginner to Advanced)\|Python Best Parts - Standard Library (Beginner to Advanced)]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Python Certification Exam PCAP-31-03 Practice Tests [2024]
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Python Certification Exam PCAP-31-03 Practice Tests [2024] | [[Learning/Programming/Python/Practice/udemy/Python Certification Exam PCAP-31-03 Practice Tests [2024]/Python Certification Exam PCAP-31-03 Practice Tests [2024]\|Python Certification Exam PCAP-31-03 Practice Tests [2024]]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Python Certification Exam PCEP-30-02 - Preparation (2025)
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Python Certification Exam PCEP-30-02 - Preparation (2025) | [[Learning/Programming/Python/Practice/udemy/Python Certification Exam PCEP-30-02 - Preparation (2025)/Python Certification Exam PCEP-30-02 - Preparation (2025)\|Python Certification Exam PCEP-30-02 - Preparation (2025)]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Python Exercises for Beginners - Solve 100+ Coding Challenges
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Python Exercises for Beginners - Solve 100+ Coding Challenges | [[Learning/Programming/Python/Practice/udemy/Python Exercises for Beginners - Solve 100+ Coding Challenges/Python Exercises for Beginners - Solve 100+ Coding Challenges\|Python Exercises for Beginners - Solve 100+ Coding Challenges]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Python Programming - 200+ Exercises for Practice
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Python Programming - 200+ Exercises for Practice | [[Learning/Programming/Python/Practice/udemy/Python Programming - 200+ Exercises for Practice/Python Programming - 200+ Exercises for Practice\|Python Programming - 200+ Exercises for Practice]] |
> > > > > 
> > 
> > > [!g-white]- Problems and Solutions
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | Problems and Solutions | [[Learning/Programming/Python/Problems and Solutions/problem 1\|problem 1]] |
> > > 
> > 
> > > [!g-white]- pyspark
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | pyspark | [[Learning/Programming/Python/pyspark/questions\|questions]] |
> > > | udemy - PySpark - Apache Spark Programming for Beginners | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 1 - Understanding Big Data and Distributed Data Processing/1. What is Big Data and How it Started\|1. What is Big Data and How it Started]] |
> > > 
> > > > [!g-white]- udemy - PySpark - Apache Spark Programming for Beginners
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | udemy - PySpark - Apache Spark Programming for Beginners | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Summary\|Summary]] |
> > > > | Section 1 - Understanding Big Data and Distributed Data Processing | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 1 - Understanding Big Data and Distributed Data Processing/1. What is Big Data and How it Started\|1. What is Big Data and How it Started]] |
> > > > | Section 10 - Spark On Your Laptop IDE | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 10 - Spark On Your Laptop IDE/49. Setup your Laptop for Spark Development\|49. Setup your Laptop for Spark Development]] |
> > > > | Section 11 - Spark Execution Model - Old Videos | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 11 - Spark Execution Model - Old Videos/52. Execution Methods - How to Run Spark Programs\|52. Execution Methods - How to Run Spark Programs]] |
> > > > | Section 12 - Spark Programming Model and Developer Experience - Old Videos | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 12 - Spark Programming Model and Developer Experience - Old Videos/60. Creating Spark Project Build Configuration\|60. Creating Spark Project Build Configuration]] |
> > > > | Section 13 - Capstone Project | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 13 - Capstone Project/69. Project Source Code and Resources\|69. Project Source Code and Resources]] |
> > > > | Section 14 - Keep Learning | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 14 - Keep Learning/80. Final Word\|80. Final Word]] |
> > > > | Section 2 - Introduction to Apache Spark | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 2 - Introduction to Apache Spark/10. Download Resources\|10. Download Resources]] |
> > > > | Section 3 - Getting Started with Spark Programming | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 3 - Getting Started with Spark Programming/11. Starting Point - Data Engineering Spark and Spark Session\|11. Starting Point - Data Engineering Spark and Spark Session]] |
> > > > | Section 4 - Spark Data Types and Schema | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 4 - Spark Data Types and Schema/17. Spark Data Types\|17. Spark Data Types]] |
> > > > | Section 5 - Dataframe Transformations | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 5 - Dataframe Transformations/21. Adding Removing and Renaming Columns\|21. Adding Removing and Renaming Columns]] |
> > > > | Section 6 - Working with different data types | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 6 - Working with different data types/27. Working with Nulls\|27. Working with Nulls]] |
> > > > | Section 7 - Joins in Spark Dataframe | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 7 - Joins in Spark Dataframe/36. Introduction to Joins in Spark\|36. Introduction to Joins in Spark]] |
> > > > | Section 8 - Aggregations in Spark Dataframe | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 8 - Aggregations in Spark Dataframe/41. Simple Aggregation\|41. Simple Aggregation]] |
> > > > | Section 9 - UDF and Unit Testing | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 9 - UDF and Unit Testing/45. User-Defined Functions\|45. User-Defined Functions]] |
> > > > 
> > > > > [!g-white]- Section 1 - Understanding Big Data and Distributed Data Processing
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 1 - Understanding Big Data and Distributed Data Processing | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 1 - Understanding Big Data and Distributed Data Processing/1. What is Big Data and How it Started\|1. What is Big Data and How it Started]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 10 - Spark On Your Laptop IDE
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 10 - Spark On Your Laptop IDE | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 10 - Spark On Your Laptop IDE/49. Setup your Laptop for Spark Development\|49. Setup your Laptop for Spark Development]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 11 - Spark Execution Model - Old Videos
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 11 - Spark Execution Model - Old Videos | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 11 - Spark Execution Model - Old Videos/52. Execution Methods - How to Run Spark Programs\|52. Execution Methods - How to Run Spark Programs]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 12 - Spark Programming Model and Developer Experience - Old Videos
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 12 - Spark Programming Model and Developer Experience - Old Videos | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 12 - Spark Programming Model and Developer Experience - Old Videos/60. Creating Spark Project Build Configuration\|60. Creating Spark Project Build Configuration]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 13 - Capstone Project
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 13 - Capstone Project | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 13 - Capstone Project/69. Project Source Code and Resources\|69. Project Source Code and Resources]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 14 - Keep Learning
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 14 - Keep Learning | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 14 - Keep Learning/80. Final Word\|80. Final Word]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 2 - Introduction to Apache Spark
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 2 - Introduction to Apache Spark | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 2 - Introduction to Apache Spark/10. Download Resources\|10. Download Resources]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 3 - Getting Started with Spark Programming
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 3 - Getting Started with Spark Programming | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 3 - Getting Started with Spark Programming/11. Starting Point - Data Engineering Spark and Spark Session\|11. Starting Point - Data Engineering Spark and Spark Session]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 4 - Spark Data Types and Schema
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 4 - Spark Data Types and Schema | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 4 - Spark Data Types and Schema/17. Spark Data Types\|17. Spark Data Types]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 5 - Dataframe Transformations
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 5 - Dataframe Transformations | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 5 - Dataframe Transformations/21. Adding Removing and Renaming Columns\|21. Adding Removing and Renaming Columns]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 6 - Working with different data types
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 6 - Working with different data types | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 6 - Working with different data types/27. Working with Nulls\|27. Working with Nulls]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 7 - Joins in Spark Dataframe
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 7 - Joins in Spark Dataframe | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 7 - Joins in Spark Dataframe/36. Introduction to Joins in Spark\|36. Introduction to Joins in Spark]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 8 - Aggregations in Spark Dataframe
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 8 - Aggregations in Spark Dataframe | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 8 - Aggregations in Spark Dataframe/41. Simple Aggregation\|41. Simple Aggregation]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 9 - UDF and Unit Testing
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 9 - UDF and Unit Testing | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 9 - UDF and Unit Testing/45. User-Defined Functions\|45. User-Defined Functions]] |
> > > > > 
> > 
> > > [!g-white]- Python Libraries and Methods
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | Python Libraries and Methods | [[Learning/Programming/Python/Python Libraries and Methods/String methods\|String methods]] |
> > > 
> > 
> > > [!g-white]- python MOC
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | python MOC | [[Learning/Programming/Python/python MOC/TODO\|TODO]] |
> > > | Advanced Python & Best Practices MOC | [[Learning/Programming/Python/python MOC/Advanced Python & Best Practices MOC/Advanced Python & Best Practices MOC\|Advanced Python & Best Practices MOC]] |
> > > | Control Flow & Functions MOC | [[Learning/Programming/Python/python MOC/Control Flow & Functions MOC/Conditionals and Booleans\|Conditionals and Booleans]] |
> > > | Data Types & Collections MOC | [[Learning/Programming/Python/python MOC/Data Types & Collections MOC/Data Types & Collections MOC\|Data Types & Collections MOC]] |
> > > | Dunder Methods & Special Functions MOC | [[Learning/Programming/Python/python MOC/Dunder Methods & Special Functions MOC/Dunder Methods & Special Functions MOC\|Dunder Methods & Special Functions MOC]] |
> > > | Exception Handling MOC | [[Learning/Programming/Python/python MOC/Exception Handling MOC/Exception Handling MOC\|Exception Handling MOC]] |
> > > | Extras Addendum MOC | [[Learning/Programming/Python/python MOC/Extras Addendum MOC/Extras Addendum MOC\|Extras Addendum MOC]] |
> > > | File Handling & Modules MOC | [[Learning/Programming/Python/python MOC/File Handling & Modules MOC/File Handling & Modules MOC\|File Handling & Modules MOC]] |
> > > | Important functions | [[Learning/Programming/Python/python MOC/Important functions/os functions\|os functions]] |
> > > | OOP MOC | [[Learning/Programming/Python/python MOC/OOP MOC/C3 Linerisation\|C3 Linerisation]] |
> > > | Operators & Expressions MOC | [[Learning/Programming/Python/python MOC/Operators & Expressions MOC/Operators & Expressions MOC\|Operators & Expressions MOC]] |
> > > | Packaging & Distribution MOC | [[Learning/Programming/Python/python MOC/Packaging & Distribution MOC/Packaging & Distribution MOC\|Packaging & Distribution MOC]] |
> > > | PyCharm | [[Learning/Programming/Python/python MOC/PyCharm/PyCharm tutorial\|PyCharm tutorial]] |
> > > | Python gotchas, epiphanies,errors,common pitfalls | [[Learning/Programming/Python/python MOC/Python gotchas, epiphanies,errors,common pitfalls/Mutable Default Arguments\|Mutable Default Arguments]] |
> > > | Python Standard Library & Utilities MOC | [[Learning/Programming/Python/python MOC/Python Standard Library & Utilities MOC/Advanced logging\|Advanced logging]] |
> > > 
> > > > [!g-white]- Advanced Python & Best Practices MOC
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Advanced Python & Best Practices MOC | [[Learning/Programming/Python/python MOC/Advanced Python & Best Practices MOC/Advanced Python & Best Practices MOC\|Advanced Python & Best Practices MOC]] |
> > > > 
> > > 
> > > > [!g-white]- Control Flow & Functions MOC
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Control Flow & Functions MOC | [[Learning/Programming/Python/python MOC/Control Flow & Functions MOC/Conditionals and Booleans\|Conditionals and Booleans]] |
> > > > 
> > > 
> > > > [!g-white]- Data Types & Collections MOC
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Data Types & Collections MOC | [[Learning/Programming/Python/python MOC/Data Types & Collections MOC/Data Types & Collections MOC\|Data Types & Collections MOC]] |
> > > > 
> > > 
> > > > [!g-white]- Dunder Methods & Special Functions MOC
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Dunder Methods & Special Functions MOC | [[Learning/Programming/Python/python MOC/Dunder Methods & Special Functions MOC/Dunder Methods & Special Functions MOC\|Dunder Methods & Special Functions MOC]] |
> > > > 
> > > 
> > > > [!g-white]- Exception Handling MOC
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Exception Handling MOC | [[Learning/Programming/Python/python MOC/Exception Handling MOC/Exception Handling MOC\|Exception Handling MOC]] |
> > > > 
> > > 
> > > > [!g-white]- Extras Addendum MOC
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Extras Addendum MOC | [[Learning/Programming/Python/python MOC/Extras Addendum MOC/Extras Addendum MOC\|Extras Addendum MOC]] |
> > > > 
> > > 
> > > > [!g-white]- File Handling & Modules MOC
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | File Handling & Modules MOC | [[Learning/Programming/Python/python MOC/File Handling & Modules MOC/File Handling & Modules MOC\|File Handling & Modules MOC]] |
> > > > | pathlib | [[Learning/Programming/Python/python MOC/File Handling & Modules MOC/pathlib/pathlib\|pathlib]] |
> > > > 
> > > > > [!g-white]- pathlib
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | pathlib | [[Learning/Programming/Python/python MOC/File Handling & Modules MOC/pathlib/pathlib\|pathlib]] |
> > > > > 
> > > 
> > > > [!g-white]- Important functions
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Important functions | [[Learning/Programming/Python/python MOC/Important functions/os functions\|os functions]] |
> > > > 
> > > 
> > > > [!g-white]- OOP MOC
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | OOP MOC | [[Learning/Programming/Python/python MOC/OOP MOC/C3 Linerisation\|C3 Linerisation]] |
> > > > 
> > > 
> > > > [!g-white]- Operators & Expressions MOC
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Operators & Expressions MOC | [[Learning/Programming/Python/python MOC/Operators & Expressions MOC/Operators & Expressions MOC\|Operators & Expressions MOC]] |
> > > > 
> > > 
> > > > [!g-white]- Packaging & Distribution MOC
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Packaging & Distribution MOC | [[Learning/Programming/Python/python MOC/Packaging & Distribution MOC/Packaging & Distribution MOC\|Packaging & Distribution MOC]] |
> > > > 
> > > 
> > > > [!g-white]- PyCharm
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | PyCharm | [[Learning/Programming/Python/python MOC/PyCharm/PyCharm tutorial\|PyCharm tutorial]] |
> > > > | plugins | [[Learning/Programming/Python/python MOC/PyCharm/plugins/ide_eval_reset\|ide_eval_reset]] |
> > > > 
> > > > > [!g-white]- plugins
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | plugins | [[Learning/Programming/Python/python MOC/PyCharm/plugins/ide_eval_reset\|ide_eval_reset]] |
> > > > > 
> > > 
> > > > [!g-white]- Python gotchas, epiphanies,errors,common pitfalls
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Python gotchas, epiphanies,errors,common pitfalls | [[Learning/Programming/Python/python MOC/Python gotchas, epiphanies,errors,common pitfalls/Mutable Default Arguments\|Mutable Default Arguments]] |
> > > > 
> > > 
> > > > [!g-white]- Python Standard Library & Utilities MOC
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Python Standard Library & Utilities MOC | [[Learning/Programming/Python/python MOC/Python Standard Library & Utilities MOC/Advanced logging\|Advanced logging]] |
> > > > | argparse | [[Learning/Programming/Python/python MOC/Python Standard Library & Utilities MOC/argparse/argparse\|argparse]] |
> > > > | BeautifulSoup module | [[Learning/Programming/Python/python MOC/Python Standard Library & Utilities MOC/BeautifulSoup module/BeautifulSoup module\|BeautifulSoup module]] |
> > > > | requests module | [[Learning/Programming/Python/python MOC/Python Standard Library & Utilities MOC/requests module/requests module\|requests module]] |
> > > > 
> > > > > [!g-white]- argparse
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | argparse | [[Learning/Programming/Python/python MOC/Python Standard Library & Utilities MOC/argparse/argparse\|argparse]] |
> > > > > 
> > > > 
> > > > > [!g-white]- BeautifulSoup module
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | BeautifulSoup module | [[Learning/Programming/Python/python MOC/Python Standard Library & Utilities MOC/BeautifulSoup module/BeautifulSoup module\|BeautifulSoup module]] |
> > > > > 
> > > > 
> > > > > [!g-white]- MoviePy
> > > > > 
> > > > > 
> > > > 
> > > > > [!g-white]- requests module
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | requests module | [[Learning/Programming/Python/python MOC/Python Standard Library & Utilities MOC/requests module/requests module\|requests module]] |
> > > > > 
> > > > 
> > > > > [!g-white]- selenium module
> > > > > 
> > > > > 
> > 
> > > [!g-white]- testing
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | testing | [[Learning/Programming/Python/testing/1. Introduction\|1. Introduction]] |
> > > | oreilly - mocking | [[Learning/Programming/Python/testing/oreilly - mocking/1. Introduction\|1. Introduction]] |
> > > | Udemy - Python Unit Testing Fundamentals | [[Learning/Programming/Python/testing/Udemy - Python Unit Testing Fundamentals/Section 1 - Unit Testing in Python/1. About This Course\|1. About This Course]] |
> > > 
> > > > [!g-white]- oreilly - mocking
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | oreilly - mocking | [[Learning/Programming/Python/testing/oreilly - mocking/1. Introduction\|1. Introduction]] |
> > > > 
> > > 
> > > > [!g-white]- Udemy - Python Unit Testing Fundamentals
> > > > 
> > > > 
> > > > > [!g-white]- Section 1 - Unit Testing in Python
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 1 - Unit Testing in Python | [[Learning/Programming/Python/testing/Udemy - Python Unit Testing Fundamentals/Section 1 - Unit Testing in Python/1. About This Course\|1. About This Course]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 10 - Reporting
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 10 - Reporting | [[Learning/Programming/Python/testing/Udemy - Python Unit Testing Fundamentals/Section 10 - Reporting/43. Module Overview\|43. Module Overview]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 11 - Course 2 - Conclusion - Unit Testing with Pytest
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 11 - Course 2 - Conclusion - Unit Testing with Pytest | [[Learning/Programming/Python/testing/Udemy - Python Unit Testing Fundamentals/Section 11 - Course 2 - Conclusion - Unit Testing with Pytest/46. Congrats\|46. Congrats]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 12 - Conclusion and Bonus
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 12 - Conclusion and Bonus | [[Learning/Programming/Python/testing/Udemy - Python Unit Testing Fundamentals/Section 12 - Conclusion and Bonus/47. Bonus\|47. Bonus]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 2 - Course 1  Start  - Python Unit Testing with unittest
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 2 - Course 1  Start  - Python Unit Testing with unittest | [[Learning/Programming/Python/testing/Udemy - Python Unit Testing Fundamentals/Section 2 - Course 1  Start  - Python Unit Testing with unittest/2. Course Resources\|2. Course Resources]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 3 - Unit Testing Fundamentals
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 3 - Unit Testing Fundamentals | [[Learning/Programming/Python/testing/Udemy - Python Unit Testing Fundamentals/Section 3 - Unit Testing Fundamentals/10. Unit Tests for a class\|10. Unit Tests for a class]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 4 - Best Practices
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 4 - Best Practices | [[Learning/Programming/Python/testing/Udemy - Python Unit Testing Fundamentals/Section 4 - Best Practices/19. Best Practices - Part 1 - Discussion\|19. Best Practices - Part 1 - Discussion]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 5 - Quiz
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 5 - Quiz | [[Learning/Programming/Python/testing/Udemy - Python Unit Testing Fundamentals/Section 5 - Quiz/Quiz 1 - Quiz\|Quiz 1 - Quiz]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 6 - Course 1 - Conclusion - Unit Testing with unittest module
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 6 - Course 1 - Conclusion - Unit Testing with unittest module | [[Learning/Programming/Python/testing/Udemy - Python Unit Testing Fundamentals/Section 6 - Course 1 - Conclusion - Unit Testing with unittest module/21. Congrats\|21. Congrats]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 7 - Course 2  Start  - Python Unit Testing with pytest
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 7 - Course 2  Start  - Python Unit Testing with pytest | [[Learning/Programming/Python/testing/Udemy - Python Unit Testing Fundamentals/Section 7 - Course 2  Start  - Python Unit Testing with pytest/22. Course Resources\|22. Course Resources]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 8 - Unit Testing with pytest
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 8 - Unit Testing with pytest | [[Learning/Programming/Python/testing/Udemy - Python Unit Testing Fundamentals/Section 8 - Unit Testing with pytest/24. Module Overview\|24. Module Overview]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 9 - Running Tests
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 9 - Running Tests | [[Learning/Programming/Python/testing/Udemy - Python Unit Testing Fundamentals/Section 9 - Running Tests/36. Module Overview\|36. Module Overview]] |
> > > > >
<!-- Python_END -->
<!-- C&T_START -->
> [!g-gray] C&T
> 
> > [!multi-column]
> > 
> > 
> > 
> > | Folder | First File Link |
> > | --- | --- |
> > |  | [[Learning/Programming/C&T/Fastest way to become a Data Engineer in 2024 - 100 Days Of Data Engineering\|Fastest way to become a Data Engineer in 2024 - 100 Days Of Data Engineering]] |
> > 
> > > [!g-white]- 365datascience.com
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | 365datascience.com | [[Learning/Programming/C&T/365datascience.com/365datascience.com\|365datascience.com]] |
> > > 
> > 
> > > [!g-white]- Database tutorial
> > > 
> > > 
> > > > [!g-white]- MongoDB
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | MongoDB | [[Learning/Programming/C&T/Database tutorial/MongoDB/Prompt Used\|Prompt Used]] |
> > > > | Section 1 - Introduction | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 1 - Introduction/1. Introduction\|1. Introduction]] |
> > > > | Section 10 - Working with Indexes | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 10 - Working with Indexes/126. Module Introduction\|126. Module Introduction]] |
> > > > | Section 11 - Working with Geospatial Data | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 11 - Working with Geospatial Data/150. Module Introduction\|150. Module Introduction]] |
> > > > | Section 12 - Understanding the Aggregation Framework | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 12 - Understanding the Aggregation Framework/160. Module Introduction\|160. Module Introduction]] |
> > > > | Section 13 - Working with Numeric Data | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 13 - Working with Numeric Data/186. Module Introduction\|186. Module Introduction]] |
> > > > | Section 14 - MongoDB & Security | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 14 - MongoDB & Security/197. Module Introduction\|197. Module Introduction]] |
> > > > | Section 15 - Performance, Fault Tolerancy & Deployment | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 15 - Performance, Fault Tolerancy & Deployment/208. Module Introduction\|208. Module Introduction]] |
> > > > | Section 16 - Transactions | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 16 - Transactions/219. Module Introduction\|219. Module Introduction]] |
> > > > | Section 17 - From Shell to Driver | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 17 - From Shell to Driver/224. Module Introduction\|224. Module Introduction]] |
> > > > | Section 18 - Introducing Stitch | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 18 - Introducing Stitch/243. Module Introduction\|243. Module Introduction]] |
> > > > | Section 19 - Roundup | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 19 - Roundup/264. Course Roundup\|264. Course Roundup]] |
> > > > | Section 2 - Understanding the Basics & CRUD Operations | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 2 - Understanding the Basics & CRUD Operations/15. Module Introduction\|15. Module Introduction]] |
> > > > | Section 3 - Schemas & Relations How to Structure Documents | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 3 - Schemas & Relations How to Structure Documents/34. Resetting Your Database\|34. Resetting Your Database]] |
> > > > | Section 4 - Exploring The Shell & The Server | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 4 - Exploring The Shell & The Server/58. Module Introduction\|58. Module Introduction]] |
> > > > | Section 5 - Using the MongoDB Compass to Explore Data Visually | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 5 - Using the MongoDB Compass to Explore Data Visually/66. Module Introduction\|66. Module Introduction]] |
> > > > | Section 6 - Diving Into Create Operations | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 6 - Diving Into Create Operations/69. Module Introduction\|69. Module Introduction]] |
> > > > | Section 7 - Read Operations - A Closer Look | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 7 - Read Operations - A Closer Look/100. Sorting Cursor Results\|100. Sorting Cursor Results]] |
> > > > | Section 8 - Update Operations | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 8 - Update Operations/106. Module Introduction\|106. Module Introduction]] |
> > > > | Section 9 - Understanding Delete Operations | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 9 - Understanding Delete Operations/122. Module Introduction\|122. Module Introduction]] |
> > > > 
> > > > > [!g-white]- Section 1 - Introduction
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 1 - Introduction | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 1 - Introduction/1. Introduction\|1. Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 10 - Working with Indexes
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 10 - Working with Indexes | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 10 - Working with Indexes/126. Module Introduction\|126. Module Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 11 - Working with Geospatial Data
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 11 - Working with Geospatial Data | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 11 - Working with Geospatial Data/150. Module Introduction\|150. Module Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 12 - Understanding the Aggregation Framework
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 12 - Understanding the Aggregation Framework | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 12 - Understanding the Aggregation Framework/160. Module Introduction\|160. Module Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 13 - Working with Numeric Data
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 13 - Working with Numeric Data | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 13 - Working with Numeric Data/186. Module Introduction\|186. Module Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 14 - MongoDB & Security
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 14 - MongoDB & Security | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 14 - MongoDB & Security/197. Module Introduction\|197. Module Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 15 - Performance, Fault Tolerancy & Deployment
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 15 - Performance, Fault Tolerancy & Deployment | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 15 - Performance, Fault Tolerancy & Deployment/208. Module Introduction\|208. Module Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 16 - Transactions
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 16 - Transactions | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 16 - Transactions/219. Module Introduction\|219. Module Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 17 - From Shell to Driver
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 17 - From Shell to Driver | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 17 - From Shell to Driver/224. Module Introduction\|224. Module Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 18 - Introducing Stitch
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 18 - Introducing Stitch | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 18 - Introducing Stitch/243. Module Introduction\|243. Module Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 19 - Roundup
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 19 - Roundup | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 19 - Roundup/264. Course Roundup\|264. Course Roundup]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 2 - Understanding the Basics & CRUD Operations
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 2 - Understanding the Basics & CRUD Operations | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 2 - Understanding the Basics & CRUD Operations/15. Module Introduction\|15. Module Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 3 - Schemas & Relations How to Structure Documents
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 3 - Schemas & Relations How to Structure Documents | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 3 - Schemas & Relations How to Structure Documents/34. Resetting Your Database\|34. Resetting Your Database]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 4 - Exploring The Shell & The Server
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 4 - Exploring The Shell & The Server | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 4 - Exploring The Shell & The Server/58. Module Introduction\|58. Module Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 5 - Using the MongoDB Compass to Explore Data Visually
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 5 - Using the MongoDB Compass to Explore Data Visually | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 5 - Using the MongoDB Compass to Explore Data Visually/66. Module Introduction\|66. Module Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 6 - Diving Into Create Operations
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 6 - Diving Into Create Operations | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 6 - Diving Into Create Operations/69. Module Introduction\|69. Module Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 7 - Read Operations - A Closer Look
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 7 - Read Operations - A Closer Look | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 7 - Read Operations - A Closer Look/100. Sorting Cursor Results\|100. Sorting Cursor Results]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 8 - Update Operations
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 8 - Update Operations | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 8 - Update Operations/106. Module Introduction\|106. Module Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 9 - Understanding Delete Operations
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 9 - Understanding Delete Operations | [[Learning/Programming/C&T/Database tutorial/MongoDB/Section 9 - Understanding Delete Operations/122. Module Introduction\|122. Module Introduction]] |
> > > > > 
> > > 
> > > > [!g-white]- PostgreSQL
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | PostgreSQL | [[Learning/Programming/C&T/Database tutorial/PostgreSQL/01 - Introduction\|01 - Introduction]] |
> > > > 
> > 
> > > [!g-white]- Domain Knowledge
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | Domain Knowledge | [[Learning/Programming/C&T/Domain Knowledge/Resources\|Resources]] |
> > > 
> > 
> > > [!g-white]- HowItsDone
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | HowItsDone | [[Learning/Programming/C&T/HowItsDone/Latex\|Latex]] |
> > > 
> > 
> > > [!g-white]- Learnbay
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | Learnbay | [[Learning/Programming/C&T/Learnbay/contact and support info\|contact and support info]] |
> > > | DL & NLP | [[Learning/Programming/C&T/Learnbay/DL & NLP/1. Class 1 , Oct 5, 2024\|1. Class 1 , Oct 5, 2024]] |
> > > | git and github | [[Learning/Programming/C&T/Learnbay/git and github/26. Class 49 , Mar 2, 2024, Sat ( Git and GitHub)\|26. Class 49 , Mar 2, 2024, Sat ( Git and GitHub)]] |
> > > | OOPS | [[Learning/Programming/C&T/Learnbay/OOPS/25. Class 47 , Feb 24, 2024, Sat ( OOPS)\|25. Class 47 , Feb 24, 2024, Sat ( OOPS)]] |
> > > | python | [[Learning/Programming/C&T/Learnbay/python/1. Class 1 , August 27, 2023 ( cohort session )\|1. Class 1 , August 27, 2023 ( cohort session )]] |
> > > | SQL & Mongo DB | [[Learning/Programming/C&T/Learnbay/SQL & Mongo DB/1.SQL & Mongo DB By Sagar- 6th July 2024\|1.SQL & Mongo DB By Sagar- 6th July 2024]] |
> > > | Statistics & Machine Learning | [[Learning/Programming/C&T/Learnbay/Statistics & Machine Learning/0. Stats By Dhruv/10.Stats & ML By Dhruv- 14 Mar 2024\|10.Stats & ML By Dhruv- 14 Mar 2024]] |
> > > 
> > > > [!g-white]- DL & NLP
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | DL & NLP | [[Learning/Programming/C&T/Learnbay/DL & NLP/1. Class 1 , Oct 5, 2024\|1. Class 1 , Oct 5, 2024]] |
> > > > 
> > > 
> > > > [!g-white]- git and github
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | git and github | [[Learning/Programming/C&T/Learnbay/git and github/26. Class 49 , Mar 2, 2024, Sat ( Git and GitHub)\|26. Class 49 , Mar 2, 2024, Sat ( Git and GitHub)]] |
> > > > 
> > > 
> > > > [!g-white]- OOPS
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | OOPS | [[Learning/Programming/C&T/Learnbay/OOPS/25. Class 47 , Feb 24, 2024, Sat ( OOPS)\|25. Class 47 , Feb 24, 2024, Sat ( OOPS)]] |
> > > > 
> > > 
> > > > [!g-white]- python
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | python | [[Learning/Programming/C&T/Learnbay/python/1. Class 1 , August 27, 2023 ( cohort session )\|1. Class 1 , August 27, 2023 ( cohort session )]] |
> > > > 
> > > 
> > > > [!g-white]- SQL & Mongo DB
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | SQL & Mongo DB | [[Learning/Programming/C&T/Learnbay/SQL & Mongo DB/1.SQL & Mongo DB By Sagar- 6th July 2024\|1.SQL & Mongo DB By Sagar- 6th July 2024]] |
> > > > 
> > > 
> > > > [!g-white]- Statistics & Machine Learning
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Statistics & Machine Learning | [[Learning/Programming/C&T/Learnbay/Statistics & Machine Learning/20. Class 37 , Jan 20, 2024, Sat ( Statistics)\|20. Class 37 , Jan 20, 2024, Sat ( Statistics)]] |
> > > > | 0. Stats By Dhruv | [[Learning/Programming/C&T/Learnbay/Statistics & Machine Learning/0. Stats By Dhruv/10.Stats & ML By Dhruv- 14 Mar 2024\|10.Stats & ML By Dhruv- 14 Mar 2024]] |
> > > > | practice | [[Learning/Programming/C&T/Learnbay/Statistics & Machine Learning/practice/28. Class 55 , Mar 17, 2024, Sun ( Machine Learning)  practice template\|28. Class 55 , Mar 17, 2024, Sun ( Machine Learning)  practice template]] |
> > > > | Tableau | [[Learning/Programming/C&T/Learnbay/Statistics & Machine Learning/Tableau/37. Class 72 , May 18, 2024, Sat ( Tablaeu)\|37. Class 72 , May 18, 2024, Sat ( Tablaeu)]] |
> > > > | Test run | [[Learning/Programming/C&T/Learnbay/Statistics & Machine Learning/Test run/Test for 28. Class 55 , Mar 17, 2024, Sun\|Test for 28. Class 55 , Mar 17, 2024, Sun]] |
> > > > 
> > > > > [!g-white]- 0. Stats By Dhruv
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | 0. Stats By Dhruv | [[Learning/Programming/C&T/Learnbay/Statistics & Machine Learning/0. Stats By Dhruv/10.Stats & ML By Dhruv- 14 Mar 2024\|10.Stats & ML By Dhruv- 14 Mar 2024]] |
> > > > > 
> > > > 
> > > > > [!g-white]- course files
> > > > > 
> > > > > 
> > > > 
> > > > > [!g-white]- practice
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | practice | [[Learning/Programming/C&T/Learnbay/Statistics & Machine Learning/practice/28. Class 55 , Mar 17, 2024, Sun ( Machine Learning)  practice template\|28. Class 55 , Mar 17, 2024, Sun ( Machine Learning)  practice template]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Tableau
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Tableau | [[Learning/Programming/C&T/Learnbay/Statistics & Machine Learning/Tableau/37. Class 72 , May 18, 2024, Sat ( Tablaeu)\|37. Class 72 , May 18, 2024, Sat ( Tablaeu)]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Test run
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Test run | [[Learning/Programming/C&T/Learnbay/Statistics & Machine Learning/Test run/Test for 28. Class 55 , Mar 17, 2024, Sun\|Test for 28. Class 55 , Mar 17, 2024, Sun]] |
> > > > > 
> > 
> > > [!g-white]- ML&AI
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | ML&AI | [[Learning/Programming/C&T/ML&AI/Interview and Preplacement Preparation\|Interview and Preplacement Preparation]] |
> > > | anaconda setup | [[Learning/Programming/C&T/ML&AI/anaconda setup/Environment name - learnbay\|Environment name - learnbay]] |
> > > | bookvideos | [[Learning/Programming/C&T/ML&AI/bookvideos/Understanding Machine Learning - From Theory to Algorithms/1 VideoNotes - Machine Learning course- Shai Ben-David： Lecture 1\|1 VideoNotes - Machine Learning course- Shai Ben-David： Lecture 1]] |
> > > | certifications that can be done | [[Learning/Programming/C&T/ML&AI/certifications that can be done/Certified Analytics Professional (CAP)\|Certified Analytics Professional (CAP)]] |
> > > | Coursera | [[Learning/Programming/C&T/ML&AI/Coursera/Machine Learning Specialization - Stanford - Deeplearning.AIM MOC/ML topics prompt\|ML topics prompt]] |
> > > | CS50 | [[Learning/Programming/C&T/ML&AI/CS50/CS50's Introduction to Artificial Intelligence with Python/1. CS50AI 2023 - Introduction\|1. CS50AI 2023 - Introduction]] |
> > > | Interview Questions | [[Learning/Programming/C&T/ML&AI/Interview Questions/Interview questions\|Interview questions]] |
> > > | Projects | [[Learning/Programming/C&T/ML&AI/Projects/coursera\|coursera]] |
> > > | Udemy - Time Series Analysis, Forecasting, and Machine Learning | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Book recommendation and Resources\|Book recommendation and Resources]] |
> > > 
> > > > [!g-white]- anaconda setup
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | anaconda setup | [[Learning/Programming/C&T/ML&AI/anaconda setup/Environment name - learnbay\|Environment name - learnbay]] |
> > > > 
> > > 
> > > > [!g-white]- bookvideos
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | bookvideos | [[Learning/Programming/C&T/ML&AI/bookvideos/bookvideos\|bookvideos]] |
> > > > | Understanding Machine Learning - From Theory to Algorithms | [[Learning/Programming/C&T/ML&AI/bookvideos/Understanding Machine Learning - From Theory to Algorithms/1 VideoNotes - Machine Learning course- Shai Ben-David： Lecture 1\|1 VideoNotes - Machine Learning course- Shai Ben-David： Lecture 1]] |
> > > > 
> > > > > [!g-white]- Understanding Machine Learning - From Theory to Algorithms
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Understanding Machine Learning - From Theory to Algorithms | [[Learning/Programming/C&T/ML&AI/bookvideos/Understanding Machine Learning - From Theory to Algorithms/1 VideoNotes - Machine Learning course- Shai Ben-David： Lecture 1\|1 VideoNotes - Machine Learning course- Shai Ben-David： Lecture 1]] |
> > > > > 
> > > 
> > > > [!g-white]- certifications that can be done
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | certifications that can be done | [[Learning/Programming/C&T/ML&AI/certifications that can be done/Certified Analytics Professional (CAP)\|Certified Analytics Professional (CAP)]] |
> > > > 
> > > 
> > > > [!g-white]- Coursera
> > > > 
> > > > 
> > > > > [!g-white]- DLS
> > > > > 
> > > > > 
> > > > 
> > > > > [!g-white]- Machine Learning Specialization - Stanford - Deeplearning.AI
> > > > > 
> > > > > 
> > > > 
> > > > > [!g-white]- Machine Learning Specialization - Stanford - Deeplearning.AIM MOC
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Machine Learning Specialization - Stanford - Deeplearning.AIM MOC | [[Learning/Programming/C&T/ML&AI/Coursera/Machine Learning Specialization - Stanford - Deeplearning.AIM MOC/ML topics prompt\|ML topics prompt]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Maths for ML & DS Specialization
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Maths for ML & DS Specialization | [[Learning/Programming/C&T/ML&AI/Coursera/Maths for ML & DS Specialization/Coursera - Mathematics for Machine Learning and Data Science Specialization - Formulas and Important points\|Coursera - Mathematics for Machine Learning and Data Science Specialization - Formulas and Important points]] |
> > > > > 
> > > 
> > > > [!g-white]- CS50
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | CS50 | [[Learning/Programming/C&T/ML&AI/CS50/CS50\|CS50]] |
> > > > | CS50's Introduction to Artificial Intelligence with Python | [[Learning/Programming/C&T/ML&AI/CS50/CS50's Introduction to Artificial Intelligence with Python/1. CS50AI 2023 - Introduction\|1. CS50AI 2023 - Introduction]] |
> > > > 
> > > > > [!g-white]- CS50's Introduction to Artificial Intelligence with Python
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | CS50's Introduction to Artificial Intelligence with Python | [[Learning/Programming/C&T/ML&AI/CS50/CS50's Introduction to Artificial Intelligence with Python/1. CS50AI 2023 - Introduction\|1. CS50AI 2023 - Introduction]] |
> > > > > 
> > > 
> > > > [!g-white]- Generative AI
> > > > 
> > > > 
> > > > > [!g-white]- linkedin what-is-generative-ai
> > > > > 
> > > > > 
> > > 
> > > > [!g-white]- Interview Questions
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Interview Questions | [[Learning/Programming/C&T/ML&AI/Interview Questions/Interview questions\|Interview questions]] |
> > > > 
> > > 
> > > > [!g-white]- Projects
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Projects | [[Learning/Programming/C&T/ML&AI/Projects/coursera\|coursera]] |
> > > > 
> > > 
> > > > [!g-white]- Udemy - Time Series Analysis, Forecasting, and Machine Learning
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Udemy - Time Series Analysis, Forecasting, and Machine Learning | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Book recommendation and Resources\|Book recommendation and Resources]] |
> > > > | Section 1 - Welcome | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 1 - Welcome/1. Introduction and Outline\|1. Introduction and Outline]] |
> > > > | Section 10 - Deep Learning - Recurrent Neural Networks (RNN) | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 10 - Deep Learning - Recurrent Neural Networks (RNN)/115. RNN Section Introduction\|115. RNN Section Introduction]] |
> > > > | Section 11 - VIP - GARCH | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 11 - VIP - GARCH/127. GARCH Section Introduction\|127. GARCH Section Introduction]] |
> > > > | Section 12 - VIP - AWS Forecast | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 12 - VIP - AWS Forecast/141. AWS Forecast Section Introduction\|141. AWS Forecast Section Introduction]] |
> > > > | Section 13 - VIP - Facebook Prophet | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 13 - VIP - Facebook Prophet/150. Prophet Section Introduction\|150. Prophet Section Introduction]] |
> > > > | Section 14 - Setting Up Your Environment FAQ | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 14 - Setting Up Your Environment FAQ/161. Pre-Installation Check\|161. Pre-Installation Check]] |
> > > > | Section 15 - Extra Help With Python Coding for Beginners FAQ | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 15 - Extra Help With Python Coding for Beginners FAQ/164. How to Code by Yourself (part 1)\|164. How to Code by Yourself (part 1)]] |
> > > > | Section 16 - Effective Learning Strategies for Machine Learning FAQ | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 16 - Effective Learning Strategies for Machine Learning FAQ/170. How to Succeed in this Course (Long Version)\|170. How to Succeed in this Course (Long Version)]] |
> > > > | Section 17 - Appendix FAQ Finale | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 17 - Appendix FAQ Finale/174. What is the Appendix\|174. What is the Appendix]] |
> > > > | Section 2 - Getting Set Up | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 2 - Getting Set Up/3. Where to get the code, notebooks, and data\|3. Where to get the code, notebooks, and data]] |
> > > > | Section 3 - Time Series Basics | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 3 - Time Series Basics/10. Types of Tasks\|10. Types of Tasks]] |
> > > > | Section 4 - Exponential Smoothing and ETS Methods | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 4 - Exponential Smoothing and ETS Methods/21. Exponential Smoothing Section Introduction\|21. Exponential Smoothing Section Introduction]] |
> > > > | Section 5 - ARIMA | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 5 - ARIMA/41. ARIMA Section Introduction\|41. ARIMA Section Introduction]] |
> > > > | Section 6 - Vector Autoregression (VAR, VMA, VARMA) | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 6 - Vector Autoregression (VAR, VMA, VARMA)/61. Vector Autoregression Section Introduction\|61. Vector Autoregression Section Introduction]] |
> > > > | Section 7 - Machine Learning Methods | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 7 - Machine Learning Methods/72. Machine Learning Section Introduction\|72. Machine Learning Section Introduction]] |
> > > > | Section 8 - Deep Learning - Artificial Neural Networks (ANN) | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 8 - Deep Learning - Artificial Neural Networks (ANN)/100. Human Activity Recognition - Feature-Based Model\|100. Human Activity Recognition - Feature-Based Model]] |
> > > > 
> > > > > [!g-white]- Section 1 - Welcome
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 1 - Welcome | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 1 - Welcome/1. Introduction and Outline\|1. Introduction and Outline]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 10 - Deep Learning - Recurrent Neural Networks (RNN)
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 10 - Deep Learning - Recurrent Neural Networks (RNN) | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 10 - Deep Learning - Recurrent Neural Networks (RNN)/115. RNN Section Introduction\|115. RNN Section Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 11 - VIP - GARCH
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 11 - VIP - GARCH | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 11 - VIP - GARCH/127. GARCH Section Introduction\|127. GARCH Section Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 12 - VIP - AWS Forecast
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 12 - VIP - AWS Forecast | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 12 - VIP - AWS Forecast/141. AWS Forecast Section Introduction\|141. AWS Forecast Section Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 13 - VIP - Facebook Prophet
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 13 - VIP - Facebook Prophet | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 13 - VIP - Facebook Prophet/150. Prophet Section Introduction\|150. Prophet Section Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 14 - Setting Up Your Environment FAQ
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 14 - Setting Up Your Environment FAQ | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 14 - Setting Up Your Environment FAQ/161. Pre-Installation Check\|161. Pre-Installation Check]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 15 - Extra Help With Python Coding for Beginners FAQ
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 15 - Extra Help With Python Coding for Beginners FAQ | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 15 - Extra Help With Python Coding for Beginners FAQ/164. How to Code by Yourself (part 1)\|164. How to Code by Yourself (part 1)]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 16 - Effective Learning Strategies for Machine Learning FAQ
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 16 - Effective Learning Strategies for Machine Learning FAQ | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 16 - Effective Learning Strategies for Machine Learning FAQ/170. How to Succeed in this Course (Long Version)\|170. How to Succeed in this Course (Long Version)]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 17 - Appendix FAQ Finale
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 17 - Appendix FAQ Finale | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 17 - Appendix FAQ Finale/174. What is the Appendix\|174. What is the Appendix]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 2 - Getting Set Up
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 2 - Getting Set Up | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 2 - Getting Set Up/3. Where to get the code, notebooks, and data\|3. Where to get the code, notebooks, and data]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 3 - Time Series Basics
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 3 - Time Series Basics | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 3 - Time Series Basics/10. Types of Tasks\|10. Types of Tasks]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 4 - Exponential Smoothing and ETS Methods
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 4 - Exponential Smoothing and ETS Methods | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 4 - Exponential Smoothing and ETS Methods/21. Exponential Smoothing Section Introduction\|21. Exponential Smoothing Section Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 5 - ARIMA
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 5 - ARIMA | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 5 - ARIMA/41. ARIMA Section Introduction\|41. ARIMA Section Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 6 - Vector Autoregression (VAR, VMA, VARMA)
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 6 - Vector Autoregression (VAR, VMA, VARMA) | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 6 - Vector Autoregression (VAR, VMA, VARMA)/61. Vector Autoregression Section Introduction\|61. Vector Autoregression Section Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 7 - Machine Learning Methods
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 7 - Machine Learning Methods | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 7 - Machine Learning Methods/72. Machine Learning Section Introduction\|72. Machine Learning Section Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 8 - Deep Learning - Artificial Neural Networks (ANN)
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 8 - Deep Learning - Artificial Neural Networks (ANN) | [[Learning/Programming/C&T/ML&AI/Udemy - Time Series Analysis, Forecasting, and Machine Learning/Section 8 - Deep Learning - Artificial Neural Networks (ANN)/100. Human Activity Recognition - Feature-Based Model\|100. Human Activity Recognition - Feature-Based Model]] |
> > > > > 
> > 
> > > [!g-white]- Trading
> > > 
> > > 
> > > > [!g-white]- QuantInsti
> > > > 
> > > > 
> > > > > [!g-white]- Dashboard - All Tracks
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Dashboard - All Tracks | [[Learning/Programming/C&T/Trading/QuantInsti/Dashboard - All Tracks/Dashboard - All Tracks\|Dashboard - All Tracks]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Webinars
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Webinars | [[Learning/Programming/C&T/Trading/QuantInsti/Webinars/QuantInsti webinar on 19,Dec 7 PM\|QuantInsti webinar on 19,Dec 7 PM]] |
> > > > > 
> > > 
> > > > [!g-white]- resources
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | resources | [[Learning/Programming/C&T/Trading/resources/aaaquants.com\|aaaquants.com]] |
> > > > 
> > > 
> > > > [!g-white]- Trainings
> > > > 
> > > > 
> > > > > [!g-white]- Tradingmarkets - Quantamentals
> > > > > 
> > > > > 
> > > 
> > > > [!g-white]- upstox
> > > > 
> > > > 
> > > > > [!g-white]- developer api
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | developer api | [[Learning/Programming/C&T/Trading/upstox/developer api/Authentication\|Authentication]] |
> > > > > 
> > > > 
> > > > > [!g-white]- mycode
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | mycode | [[Learning/Programming/C&T/Trading/upstox/mycode/progressing\|progressing]] |
> > > > > 
> > > 
> > > > [!g-white]- zerodha varsity
> > > > 
> > > > 
> > > > > [!g-white]- 1. Introduction to Stock Markets
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | 1. Introduction to Stock Markets | [[Learning/Programming/C&T/Trading/zerodha varsity/1. Introduction to Stock Markets/1. The Need to Invest\|1. The Need to Invest]] |
> > > > > 
> > > > 
> > > > > [!g-white]- 2. Technical Analysis
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | 2. Technical Analysis | [[Learning/Programming/C&T/Trading/zerodha varsity/2. Technical Analysis/13. Moving Averages\|13. Moving Averages]] |
> > > > > 
> > 
> > > [!g-white]- web development
> > > 
> > > 
> > > > [!g-white]- css youtube
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | css youtube | [[Learning/Programming/C&T/web development/css youtube/HTML5 and CSS3 - 33 - Width, Max-Width, Min-Width - YouTube\|HTML5 and CSS3 - 33 - Width, Max-Width, Min-Width - YouTube]] |
> > > > 
> > > 
> > > > [!g-white]- Javascript
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Javascript | [[Learning/Programming/C&T/web development/Javascript/async\|async]] |
> > > > 
> > > > > [!g-white]- JavaScript - The Complete Guide 2025
> > > > > 
> > > > > 
> > > > 
> > > > > [!g-white]- JavaScript - The Complete Guide 2025 (Beginner + Advanced)
> > > > > 
> > > > > 
> > > 
> > > > [!g-white]- Kevin Powell
> > > > 
> > > > 
> > > > > [!g-white]- CSS Demystified - Start Writing CSS with Confidence (Module 1-3)
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | CSS Demystified - Start Writing CSS with Confidence (Module 1-3) | [[Learning/Programming/C&T/web development/Kevin Powell/CSS Demystified - Start Writing CSS with Confidence (Module 1-3)/Untitled\|Untitled]] |
> > > > >
<!-- C&T_END -->

<!-- Git and Github_START -->
> [!g-gray] Git and Github
> 
> > [!multi-column]
> > 
> > 
> > No files
> > 
> > > [!g-white]- The Git and Github Bootcamp
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | The Git and Github Bootcamp | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/The Git & Github Bootcamp MOC\|The Git & Github Bootcamp MOC]] |
> > > | section 1 - Course Orientation | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 1 - Course Orientation/1. Welcome To The Course!\|1. Welcome To The Course!]] |
> > > | section 10 - Undoing Changes & Time Traveling | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 10 - Undoing Changes & Time Traveling/81. What Really Matters In This Section\|81. What Really Matters In This Section]] |
> > > | section 11 - Github - The Basics | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 11 - Github - The Basics/100. Touring A Github Repo\|100. Touring A Github Repo]] |
> > > | section 12 - Fetching & Pulling | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 12 - Fetching & Pulling/107. What Really Matters In This Section\|107. What Really Matters In This Section]] |
> > > | section 13 - Github Grab Bag - Odds & Ends | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 13 - Github Grab Bag - Odds & Ends/116. What Really Matters In This Section\|116. What Really Matters In This Section]] |
> > > | section 14 - Git Collaboration Workflows | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 14 - Git Collaboration Workflows/126. What Really Matters In This Section\|126. What Really Matters In This Section]] |
> > > | section 15 - Rebasing - The Scariest Git Command | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 15 - Rebasing - The Scariest Git Command/140. What Really Matters In This Section\|140. What Really Matters In This Section]] |
> > > | section 16 - Cleaning Up History With Interactive Rebase | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 16 - Cleaning Up History With Interactive Rebase/147. What Really Matters In This Section\|147. What Really Matters In This Section]] |
> > > | section 17 - Git Tags - Marking Important Moments In History | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 17 - Git Tags - Marking Important Moments In History/152. What Really Matters In This Section\|152. What Really Matters In This Section]] |
> > > | section 18 - Git Behind The Scenes - Hashing & Objects | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 18 - Git Behind The Scenes - Hashing & Objects/163. What Really Matters In This Section\|163. What Really Matters In This Section]] |
> > > | section 19 - The Power of Reflogs - Retrieving Lost Work | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 19 - The Power of Reflogs - Retrieving Lost Work/175. What Really Matters In This Section\|175. What Really Matters In This Section]] |
> > > | section 2 - Introducing...Git! | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 2 - Introducing...Git!/10. Who Uses Git\|10. Who Uses Git]] |
> > > | section 20 - Writing Custom Git Aliases | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 20 - Writing Custom Git Aliases/183. What Matters In This Section\|183. What Matters In This Section]] |
> > > | section 3 - Installation & Setup | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 3 - Installation & Setup/12. What Really Matters In This Section\|12. What Really Matters In This Section]] |
> > > | section 4 - The Very Basics Of Git - Adding & Committing | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 4 - The Very Basics Of Git - Adding & Committing/22. What Really Matters In This Section\|22. What Really Matters In This Section]] |
> > > | section 5 - Commits In Detail (And Related Topics) | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 5 - Commits In Detail (And Related Topics)/32. What Really Matters In This Section\|32. What Really Matters In This Section]] |
> > > | section 6 - Working With Branches | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 6 - Working With Branches/41. What Really Matters In This Section\|41. What Really Matters In This Section]] |
> > > | section 7 - Merging Branches, Oh Boy! | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 7 - Merging Branches, Oh Boy!/53. What Really Matters In This Section\|53. What Really Matters In This Section]] |
> > > | section 8 - Comparing Changes With Git Diff | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 8 - Comparing Changes With Git Diff/62. What Really Matters In This Section\|62. What Really Matters In This Section]] |
> > > | section 9 - The Ins and Outs of Stashing | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 9 - The Ins and Outs of Stashing/73. What Really Matters In This Section\|73. What Really Matters In This Section]] |
> > > 
> > > > [!g-white]- section 1 - Course Orientation
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | section 1 - Course Orientation | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 1 - Course Orientation/1. Welcome To The Course!\|1. Welcome To The Course!]] |
> > > > 
> > > 
> > > > [!g-white]- section 10 - Undoing Changes & Time Traveling
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | section 10 - Undoing Changes & Time Traveling | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 10 - Undoing Changes & Time Traveling/81. What Really Matters In This Section\|81. What Really Matters In This Section]] |
> > > > 
> > > 
> > > > [!g-white]- section 11 - Github - The Basics
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | section 11 - Github - The Basics | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 11 - Github - The Basics/100. Touring A Github Repo\|100. Touring A Github Repo]] |
> > > > 
> > > 
> > > > [!g-white]- section 12 - Fetching & Pulling
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | section 12 - Fetching & Pulling | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 12 - Fetching & Pulling/107. What Really Matters In This Section\|107. What Really Matters In This Section]] |
> > > > 
> > > 
> > > > [!g-white]- section 13 - Github Grab Bag - Odds & Ends
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | section 13 - Github Grab Bag - Odds & Ends | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 13 - Github Grab Bag - Odds & Ends/116. What Really Matters In This Section\|116. What Really Matters In This Section]] |
> > > > 
> > > 
> > > > [!g-white]- section 14 - Git Collaboration Workflows
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | section 14 - Git Collaboration Workflows | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 14 - Git Collaboration Workflows/126. What Really Matters In This Section\|126. What Really Matters In This Section]] |
> > > > 
> > > 
> > > > [!g-white]- section 15 - Rebasing - The Scariest Git Command
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | section 15 - Rebasing - The Scariest Git Command | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 15 - Rebasing - The Scariest Git Command/140. What Really Matters In This Section\|140. What Really Matters In This Section]] |
> > > > 
> > > 
> > > > [!g-white]- section 16 - Cleaning Up History With Interactive Rebase
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | section 16 - Cleaning Up History With Interactive Rebase | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 16 - Cleaning Up History With Interactive Rebase/147. What Really Matters In This Section\|147. What Really Matters In This Section]] |
> > > > 
> > > 
> > > > [!g-white]- section 17 - Git Tags - Marking Important Moments In History
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | section 17 - Git Tags - Marking Important Moments In History | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 17 - Git Tags - Marking Important Moments In History/152. What Really Matters In This Section\|152. What Really Matters In This Section]] |
> > > > 
> > > 
> > > > [!g-white]- section 18 - Git Behind The Scenes - Hashing & Objects
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | section 18 - Git Behind The Scenes - Hashing & Objects | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 18 - Git Behind The Scenes - Hashing & Objects/163. What Really Matters In This Section\|163. What Really Matters In This Section]] |
> > > > 
> > > 
> > > > [!g-white]- section 19 - The Power of Reflogs - Retrieving Lost Work
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | section 19 - The Power of Reflogs - Retrieving Lost Work | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 19 - The Power of Reflogs - Retrieving Lost Work/175. What Really Matters In This Section\|175. What Really Matters In This Section]] |
> > > > 
> > > 
> > > > [!g-white]- section 2 - Introducing...Git!
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | section 2 - Introducing...Git! | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 2 - Introducing...Git!/10. Who Uses Git\|10. Who Uses Git]] |
> > > > 
> > > 
> > > > [!g-white]- section 20 - Writing Custom Git Aliases
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | section 20 - Writing Custom Git Aliases | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 20 - Writing Custom Git Aliases/183. What Matters In This Section\|183. What Matters In This Section]] |
> > > > 
> > > 
> > > > [!g-white]- section 3 - Installation & Setup
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | section 3 - Installation & Setup | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 3 - Installation & Setup/12. What Really Matters In This Section\|12. What Really Matters In This Section]] |
> > > > 
> > > 
> > > > [!g-white]- section 4 - The Very Basics Of Git - Adding & Committing
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | section 4 - The Very Basics Of Git - Adding & Committing | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 4 - The Very Basics Of Git - Adding & Committing/22. What Really Matters In This Section\|22. What Really Matters In This Section]] |
> > > > 
> > > 
> > > > [!g-white]- section 5 - Commits In Detail (And Related Topics)
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | section 5 - Commits In Detail (And Related Topics) | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 5 - Commits In Detail (And Related Topics)/32. What Really Matters In This Section\|32. What Really Matters In This Section]] |
> > > > 
> > > 
> > > > [!g-white]- section 6 - Working With Branches
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | section 6 - Working With Branches | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 6 - Working With Branches/41. What Really Matters In This Section\|41. What Really Matters In This Section]] |
> > > > 
> > > 
> > > > [!g-white]- section 7 - Merging Branches, Oh Boy!
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | section 7 - Merging Branches, Oh Boy! | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 7 - Merging Branches, Oh Boy!/53. What Really Matters In This Section\|53. What Really Matters In This Section]] |
> > > > 
> > > 
> > > > [!g-white]- section 8 - Comparing Changes With Git Diff
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | section 8 - Comparing Changes With Git Diff | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 8 - Comparing Changes With Git Diff/62. What Really Matters In This Section\|62. What Really Matters In This Section]] |
> > > > 
> > > 
> > > > [!g-white]- section 9 - The Ins and Outs of Stashing
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | section 9 - The Ins and Outs of Stashing | [[Learning/Programming/Git and Github/The Git and Github Bootcamp/section 9 - The Ins and Outs of Stashing/73. What Really Matters In This Section\|73. What Really Matters In This Section]] |
> > > >
<!-- Git and Github_END -->

<!-- Miscellaneous_START -->
> [!g-gray] Miscellaneous
> 
> > [!multi-column]
> > 
> > 
> > No files
> > 
> > > [!g-white]- AI PC setup
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | AI PC setup | [[Learning/Programming/Miscellaneous/AI PC setup/EPYC 9335 build\|EPYC 9335 build]] |
> > > | LLAMA3 | [[Learning/Programming/Miscellaneous/AI PC setup/LLAMA3/Calculating GPU memory for serving LLMs\|Calculating GPU memory for serving LLMs]] |
> > > | Write my book on it | [[Learning/Programming/Miscellaneous/AI PC setup/Write my book on it/1. Building a ML&AI Computer System - Chapter 1 - Introduction\|1. Building a ML&AI Computer System - Chapter 1 - Introduction]] |
> > > 
> > > > [!g-white]- LLAMA3
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | LLAMA3 | [[Learning/Programming/Miscellaneous/AI PC setup/LLAMA3/Calculating GPU memory for serving LLMs\|Calculating GPU memory for serving LLMs]] |
> > > > 
> > > 
> > > > [!g-white]- Write my book on it
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Write my book on it | [[Learning/Programming/Miscellaneous/AI PC setup/Write my book on it/1. Building a ML&AI Computer System - Chapter 1 - Introduction\|1. Building a ML&AI Computer System - Chapter 1 - Introduction]] |
> > > > 
> > 
> > > [!g-white]- RHCSA, RHCE
> > > 
> > > 
> > > > [!g-white]- books
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | books | [[Learning/Programming/Miscellaneous/RHCSA, RHCE/books/Red Hat RHCSA 9 Cert Guide - EX200 by Sander van Vugt\|Red Hat RHCSA 9 Cert Guide - EX200 by Sander van Vugt]] |
> > > > 
> > 
> > > [!g-white]- RHEL 9
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | RHEL 9 | [[Learning/Programming/Miscellaneous/RHEL 9/Configuring samba\|Configuring samba]] |
> > > | tests | [[Learning/Programming/Miscellaneous/RHEL 9/tests/Tutorial on git\|Tutorial on git]] |
> > > 
> > > > [!g-white]- tests
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | tests | [[Learning/Programming/Miscellaneous/RHEL 9/tests/Tutorial on git\|Tutorial on git]] |
> > > > 
> > 
> > > [!g-white]- Usefull information, Problems and KYC
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | Usefull information, Problems and KYC | [[Learning/Programming/Miscellaneous/Usefull information, Problems and KYC/Clone drives and partitions to another drive\|Clone drives and partitions to another drive]] |
> > > | epub editing | [[Learning/Programming/Miscellaneous/Usefull information, Problems and KYC/epub editing/creating expandable\|creating expandable]] |
> > > | Income tax efiling | [[Learning/Programming/Miscellaneous/Usefull information, Problems and KYC/Income tax efiling/Section 1 - Introduction/1. Introduction\|1. Introduction]] |
> > > | Kasm workspaces with cloudflare | [[Learning/Programming/Miscellaneous/Usefull information, Problems and KYC/Kasm workspaces with cloudflare/Allow origin Domain and Upstream Auth Address\|Allow origin Domain and Upstream Auth Address]] |
> > > | linux problems and tasks | [[Learning/Programming/Miscellaneous/Usefull information, Problems and KYC/linux problems and tasks/Custom icons\|Custom icons]] |
> > > 
> > > > [!g-white]- epub editing
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | epub editing | [[Learning/Programming/Miscellaneous/Usefull information, Problems and KYC/epub editing/creating expandable\|creating expandable]] |
> > > > 
> > > 
> > > > [!g-white]- Income tax efiling
> > > > 
> > > > 
> > > > > [!g-white]- Section 1 - Introduction
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 1 - Introduction | [[Learning/Programming/Miscellaneous/Usefull information, Problems and KYC/Income tax efiling/Section 1 - Introduction/1. Introduction\|1. Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 2 - E-Filing Basics
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 2 - E-Filing Basics | [[Learning/Programming/Miscellaneous/Usefull information, Problems and KYC/Income tax efiling/Section 2 - E-Filing Basics/2. Introduction to e-Filing Portal & Income Tax Utilities\|2. Introduction to e-Filing Portal & Income Tax Utilities]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 3 - Individual Tax Return Filing
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 3 - Individual Tax Return Filing | [[Learning/Programming/Miscellaneous/Usefull information, Problems and KYC/Income tax efiling/Section 3 - Individual Tax Return Filing/3. ITR-1-Online and Offline Filing\|3. ITR-1-Online and Offline Filing]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 4 - Advanced Tax Topics
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 4 - Advanced Tax Topics | [[Learning/Programming/Miscellaneous/Usefull information, Problems and KYC/Income tax efiling/Section 4 - Advanced Tax Topics/10. Selection of ITR Forms in Detail and Form 29B\|10. Selection of ITR Forms in Detail and Form 29B]] |
> > > > > 
> > > 
> > > > [!g-white]- Kasm workspaces with cloudflare
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Kasm workspaces with cloudflare | [[Learning/Programming/Miscellaneous/Usefull information, Problems and KYC/Kasm workspaces with cloudflare/Allow origin Domain and Upstream Auth Address\|Allow origin Domain and Upstream Auth Address]] |
> > > > 
> > > 
> > > > [!g-white]- linux problems and tasks
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | linux problems and tasks | [[Learning/Programming/Miscellaneous/Usefull information, Problems and KYC/linux problems and tasks/Custom icons\|Custom icons]] |
> > > > | Linux problems and resolutions | [[Learning/Programming/Miscellaneous/Usefull information, Problems and KYC/linux problems and tasks/Linux problems and resolutions/Bridged network for guest KVM's\|Bridged network for guest KVM's]] |
> > > > 
> > > > > [!g-white]- Image slider
> > > > > 
> > > > > 
> > > > 
> > > > > [!g-white]- Linux problems and resolutions
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Linux problems and resolutions | [[Learning/Programming/Miscellaneous/Usefull information, Problems and KYC/linux problems and tasks/Linux problems and resolutions/Bridged network for guest KVM's\|Bridged network for guest KVM's]] |
> > > > >
<!-- Miscellaneous_END -->

<!-- Python_START -->
> [!g-gray] Python
> 
> > [!multi-column]
> > 
> > 
> > 
> > | Folder | First File Link |
> > | --- | --- |
> > |  | [[Learning/Programming/Python/Other python links in vault\|Other python links in vault]] |
> > 
> > > [!g-white]- Automate Excel Using Python
> > > 
> > > 
> > > > [!g-white]- Section 1 - Introduction
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 1 - Introduction | [[Learning/Programming/Python/Automate Excel Using Python/Section 1 - Introduction/1. Introduction\|1. Introduction]] |
> > > > 
> > > 
> > > > [!g-white]- Section 10 - Add Formulas
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 10 - Add Formulas | [[Learning/Programming/Python/Automate Excel Using Python/Section 10 - Add Formulas/45. Add Formulas to the cell\|45. Add Formulas to the cell]] |
> > > > 
> > > 
> > > > [!g-white]- Section 11 - Filter Operations
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 11 - Filter Operations | [[Learning/Programming/Python/Automate Excel Using Python/Section 11 - Filter Operations/46. Filter Operations.\|46. Filter Operations.]] |
> > > > 
> > > 
> > > > [!g-white]- Section 12 - Charts
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 12 - Charts | [[Learning/Programming/Python/Automate Excel Using Python/Section 12 - Charts/47. Create Pie Charts\|47. Create Pie Charts]] |
> > > > 
> > > 
> > > > [!g-white]- Section 13 - Manipulating Worksheet
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 13 - Manipulating Worksheet | [[Learning/Programming/Python/Automate Excel Using Python/Section 13 - Manipulating Worksheet/52. Deleting Rows and Columns\|52. Deleting Rows and Columns]] |
> > > > 
> > > 
> > > > [!g-white]- Section 14 - Data Iterating
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 14 - Data Iterating | [[Learning/Programming/Python/Automate Excel Using Python/Section 14 - Data Iterating/54. Iterating Data of Columns and Rows.\|54. Iterating Data of Columns and Rows.]] |
> > > > 
> > > 
> > > > [!g-white]- Section 15 - Read and Write Operations from different files
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 15 - Read and Write Operations from different files | [[Learning/Programming/Python/Automate Excel Using Python/Section 15 - Read and Write Operations from different files/56. Copy Data from one sheet to another sheet.\|56. Copy Data from one sheet to another sheet.]] |
> > > > 
> > > 
> > > > [!g-white]- Section 2 - Configuration softwares for Windows and Mac
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 2 - Configuration softwares for Windows and Mac | [[Learning/Programming/Python/Automate Excel Using Python/Section 2 - Configuration softwares for Windows and Mac/2. List of softwares required for configuration\|2. List of softwares required for configuration]] |
> > > > 
> > > 
> > > > [!g-white]- Section 3 - Python Basics
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 3 - Python Basics | [[Learning/Programming/Python/Automate Excel Using Python/Section 3 - Python Basics/10. Variables\|10. Variables]] |
> > > > 
> > > 
> > > > [!g-white]- Section 4 - Overview on Workbook and Worksheet
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 4 - Overview on Workbook and Worksheet | [[Learning/Programming/Python/Automate Excel Using Python/Section 4 - Overview on Workbook and Worksheet/30. Create Workbook and Worksheet\|30. Create Workbook and Worksheet]] |
> > > > 
> > > 
> > > > [!g-white]- Section 5 - Write Operations
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 5 - Write Operations | [[Learning/Programming/Python/Automate Excel Using Python/Section 5 - Write Operations/33. Write the data in cells\|33. Write the data in cells]] |
> > > > 
> > > 
> > > > [!g-white]- Section 6 - Read Operations
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 6 - Read Operations | [[Learning/Programming/Python/Automate Excel Using Python/Section 6 - Read Operations/35. Read the data from the Excel file.\|35. Read the data from the Excel file.]] |
> > > > 
> > > 
> > > > [!g-white]- Section 7 - Comments in Excel sheet
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 7 - Comments in Excel sheet | [[Learning/Programming/Python/Automate Excel Using Python/Section 7 - Comments in Excel sheet/38. Add the comments to the cell.\|38. Add the comments to the cell.]] |
> > > > 
> > > 
> > > > [!g-white]- Section 8 - Add Styles to Excel sheet data
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 8 - Add Styles to Excel sheet data | [[Learning/Programming/Python/Automate Excel Using Python/Section 8 - Add Styles to Excel sheet data/39. Part 1 - Styles to the text data in Excel sheet - Bold , Italic ,Underline, etc\|39. Part 1 - Styles to the text data in Excel sheet - Bold , Italic ,Underline, etc]] |
> > > > 
> > > 
> > > > [!g-white]- Section 9 - Add Image to excel file
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 9 - Add Image to excel file | [[Learning/Programming/Python/Automate Excel Using Python/Section 9 - Add Image to excel file/44. Add image to excel file.\|44. Add image to excel file.]] |
> > > > 
> > 
> > > [!g-white]- Automating networks
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | Automating networks | [[Learning/Programming/Python/Automating networks/Automating networks\|Automating networks]] |
> > > | Master Network Automation with Python for Network Engineers | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Master Network Automation with Python for Network Engineers\|Master Network Automation with Python for Network Engineers]] |
> > > | Mastering Python Networking | [[Learning/Programming/Python/Automating networks/Mastering Python Networking/Mastering Python Networking\|Mastering Python Networking]] |
> > > | Python Programming for Network Engineers - Cisco, Netmiko ++ | [[Learning/Programming/Python/Automating networks/Python Programming for Network Engineers - Cisco, Netmiko ++/Python Programming for Network Engineers - Cisco, Netmiko ++\|Python Programming for Network Engineers - Cisco, Netmiko ++]] |
> > > 
> > > > [!g-white]- Master Network Automation with Python for Network Engineers
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Master Network Automation with Python for Network Engineers | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Master Network Automation with Python for Network Engineers\|Master Network Automation with Python for Network Engineers]] |
> > > > | Section 1 - Course Introduction | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 1 - Course Introduction/1. Why Network Automation with Python Why Now\|1. Why Network Automation with Python Why Now]] |
> > > > | Section 10 - Building Concurrent Applications Using Async IO | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 10 - Building Concurrent Applications Using Async IO/100. Coding - Running Shell Commands\|100. Coding - Running Shell Commands]] |
> > > > | Section 11 - [Appendix] - Running Arista vEOS and Juniper vSRX in GNS3 | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 11 - [Appendix] - Running Arista vEOS and Juniper vSRX in GNS3/104. How to Run Arista vEOS in GNS3\|104. How to Run Arista vEOS in GNS3]] |
> > > > | Section 12 - Network Automation with Napalm | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 12 - Network Automation with Napalm/110. Intro to Napalm\|110. Intro to Napalm]] |
> > > > | Section 13 - Network Automation with Telnet | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 13 - Network Automation with Telnet/118. Bytes Objects, Encoding and Decoding\|118. Bytes Objects, Encoding and Decoding]] |
> > > > | Section 14 - Hands-On Challenges - Network Automation with Telnet | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 14 - Hands-On Challenges - Network Automation with Telnet/127. Hands-On Challenges - Telnet\|127. Hands-On Challenges - Telnet]] |
> > > > | Section 15 - Network Automation Using Serial Connections | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 15 - Network Automation Using Serial Connections/128. Serial Communication Basics. Connecting to a Console Port\|128. Serial Communication Basics. Connecting to a Console Port]] |
> > > > | Section 16 - [Appendix] Useful Python Modules | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 16 - [Appendix] Useful Python Modules/135. System-specific Parameters and Functions - The Sys Module\|135. System-specific Parameters and Functions - The Sys Module]] |
> > > > | Section 17 - [Appendix] - SSH Public Key Authentication (Cisco IOS & Linux) | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 17 - [Appendix] - SSH Public Key Authentication (Cisco IOS & Linux)/140. SSH Public Key Authentication Overview\|140. SSH Public Key Authentication Overview]] |
> > > > | Section 18 - [Appendix] - Ansible - Automate for Everyone | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 18 - [Appendix] - Ansible - Automate for Everyone/147. About This Section\|147. About This Section]] |
> > > > | Section 19 - [Appendix] - Ansible Playbooks | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 19 - [Appendix] - Ansible Playbooks/157. YAML Files\|157. YAML Files]] |
> > > > | Section 2 - Setup the Environment - Python, PyCharm, GNS3, Cisco IOU and | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 2 - Setup the Environment - Python, PyCharm, GNS3, Cisco IOU and/10. Installing Python 3 on Windows\|10. Installing Python 3 on Windows]] |
> > > > | Section 20 - [Python Programming] - Python Basics | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 20 - [Python Programming] - Python Basics/172. Quick Note for Beginners\|172. Quick Note for Beginners]] |
> > > > | Section 21 - [Python Programming] - Strings in Python | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 21 - [Python Programming] - Strings in Python/186. Intro to Strings\|186. Intro to Strings]] |
> > > > | Section 22 - [Python Programming] - Program Flow Control | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 22 - [Python Programming] - Program Flow Control/195. Conditional Statements\|195. Conditional Statements]] |
> > > > | Section 23 - [Python Programming] Python Loops | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 23 - [Python Programming] Python Loops/201. For Loops\|201. For Loops]] |
> > > > | Section 24 - [Python Programming] - Lists and Tuples in Python | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 24 - [Python Programming] - Lists and Tuples in Python/211. Intro to Lists\|211. Intro to Lists]] |
> > > > | Section 25 - [Python Programming] - Sets, Frozensets and Dictionaries in Python | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 25 - [Python Programming] - Sets, Frozensets and Dictionaries in Python/223. Intro to Sets\|223. Intro to Sets]] |
> > > > | Section 26 - [Python Programming] - Functions in Python | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 26 - [Python Programming] - Functions in Python/232. Intro to Functions\|232. Intro to Functions]] |
> > > > | Section 27 - [Python Programming] - Errors and Exception Handling | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 27 - [Python Programming] - Errors and Exception Handling/241. Intro to Exceptions\|241. Intro to Exceptions]] |
> > > > | Section 28 - [Python Programming] - Object Oriented Programming Basics | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 28 - [Python Programming] - Object Oriented Programming Basics/245. Intro to Object Oriented Programming\|245. Intro to Object Oriented Programming]] |
> > > > | Section 29 - BONUS SECTION | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 29 - BONUS SECTION/251. Congratulations\|251. Congratulations]] |
> > > > | Section 3 - Working with Text Files In Python | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 3 - Working with Text Files In Python/26. Intro\|26. Intro]] |
> > > > | Section 4 - Hands-On Challenges - Working With Files | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 4 - Hands-On Challenges - Working With Files/42. Hands-On Challenges - Working with Text Files\|42. Hands-On Challenges - Working with Text Files]] |
> > > > | Section 5 - Data Serialization and Deserialization In Python (Pickle and...) | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 5 - Data Serialization and Deserialization In Python (Pickle and...)/44. Intro to Data Serialization\|44. Intro to Data Serialization]] |
> > > > | Section 6 - Network Automation with Paramiko (SSH) | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 6 - Network Automation with Paramiko (SSH)/56. The Lab Environment\|56. The Lab Environment]] |
> > > > | Section 7 - Hands-On Challenges - Network Automation with Paramiko | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 7 - Hands-On Challenges - Network Automation with Paramiko/76. Hands-On Challenges - Paramiko\|76. Hands-On Challenges - Paramiko]] |
> > > > | Section 8 - Network Automation with Netmiko (SSH) | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 8 - Network Automation with Netmiko (SSH)/77. The Lab Environment\|77. The Lab Environment]] |
> > > > | Section 9 - Hands-On Challenges - Network Automation with Netmiko | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 9 - Hands-On Challenges - Network Automation with Netmiko/93. Hands-On Challenges - Netmiko\|93. Hands-On Challenges - Netmiko]] |
> > > > 
> > > > > [!g-white]- Section 1 - Course Introduction
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 1 - Course Introduction | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 1 - Course Introduction/1. Why Network Automation with Python Why Now\|1. Why Network Automation with Python Why Now]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 10 - Building Concurrent Applications Using Async IO
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 10 - Building Concurrent Applications Using Async IO | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 10 - Building Concurrent Applications Using Async IO/100. Coding - Running Shell Commands\|100. Coding - Running Shell Commands]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 11 - [Appendix] - Running Arista vEOS and Juniper vSRX in GNS3
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 11 - [Appendix] - Running Arista vEOS and Juniper vSRX in GNS3 | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 11 - [Appendix] - Running Arista vEOS and Juniper vSRX in GNS3/104. How to Run Arista vEOS in GNS3\|104. How to Run Arista vEOS in GNS3]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 12 - Network Automation with Napalm
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 12 - Network Automation with Napalm | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 12 - Network Automation with Napalm/110. Intro to Napalm\|110. Intro to Napalm]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 13 - Network Automation with Telnet
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 13 - Network Automation with Telnet | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 13 - Network Automation with Telnet/118. Bytes Objects, Encoding and Decoding\|118. Bytes Objects, Encoding and Decoding]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 14 - Hands-On Challenges - Network Automation with Telnet
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 14 - Hands-On Challenges - Network Automation with Telnet | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 14 - Hands-On Challenges - Network Automation with Telnet/127. Hands-On Challenges - Telnet\|127. Hands-On Challenges - Telnet]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 15 - Network Automation Using Serial Connections
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 15 - Network Automation Using Serial Connections | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 15 - Network Automation Using Serial Connections/128. Serial Communication Basics. Connecting to a Console Port\|128. Serial Communication Basics. Connecting to a Console Port]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 16 - [Appendix] Useful Python Modules
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 16 - [Appendix] Useful Python Modules | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 16 - [Appendix] Useful Python Modules/135. System-specific Parameters and Functions - The Sys Module\|135. System-specific Parameters and Functions - The Sys Module]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 17 - [Appendix] - SSH Public Key Authentication (Cisco IOS & Linux)
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 17 - [Appendix] - SSH Public Key Authentication (Cisco IOS & Linux) | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 17 - [Appendix] - SSH Public Key Authentication (Cisco IOS & Linux)/140. SSH Public Key Authentication Overview\|140. SSH Public Key Authentication Overview]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 18 - [Appendix] - Ansible - Automate for Everyone
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 18 - [Appendix] - Ansible - Automate for Everyone | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 18 - [Appendix] - Ansible - Automate for Everyone/147. About This Section\|147. About This Section]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 19 - [Appendix] - Ansible Playbooks
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 19 - [Appendix] - Ansible Playbooks | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 19 - [Appendix] - Ansible Playbooks/157. YAML Files\|157. YAML Files]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 2 - Setup the Environment - Python, PyCharm, GNS3, Cisco IOU and
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 2 - Setup the Environment - Python, PyCharm, GNS3, Cisco IOU and | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 2 - Setup the Environment - Python, PyCharm, GNS3, Cisco IOU and/10. Installing Python 3 on Windows\|10. Installing Python 3 on Windows]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 20 - [Python Programming] - Python Basics
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 20 - [Python Programming] - Python Basics | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 20 - [Python Programming] - Python Basics/172. Quick Note for Beginners\|172. Quick Note for Beginners]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 21 - [Python Programming] - Strings in Python
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 21 - [Python Programming] - Strings in Python | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 21 - [Python Programming] - Strings in Python/186. Intro to Strings\|186. Intro to Strings]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 22 - [Python Programming] - Program Flow Control
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 22 - [Python Programming] - Program Flow Control | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 22 - [Python Programming] - Program Flow Control/195. Conditional Statements\|195. Conditional Statements]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 23 - [Python Programming] Python Loops
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 23 - [Python Programming] Python Loops | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 23 - [Python Programming] Python Loops/201. For Loops\|201. For Loops]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 24 - [Python Programming] - Lists and Tuples in Python
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 24 - [Python Programming] - Lists and Tuples in Python | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 24 - [Python Programming] - Lists and Tuples in Python/211. Intro to Lists\|211. Intro to Lists]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 25 - [Python Programming] - Sets, Frozensets and Dictionaries in Python
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 25 - [Python Programming] - Sets, Frozensets and Dictionaries in Python | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 25 - [Python Programming] - Sets, Frozensets and Dictionaries in Python/223. Intro to Sets\|223. Intro to Sets]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 26 - [Python Programming] - Functions in Python
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 26 - [Python Programming] - Functions in Python | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 26 - [Python Programming] - Functions in Python/232. Intro to Functions\|232. Intro to Functions]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 27 - [Python Programming] - Errors and Exception Handling
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 27 - [Python Programming] - Errors and Exception Handling | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 27 - [Python Programming] - Errors and Exception Handling/241. Intro to Exceptions\|241. Intro to Exceptions]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 28 - [Python Programming] - Object Oriented Programming Basics
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 28 - [Python Programming] - Object Oriented Programming Basics | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 28 - [Python Programming] - Object Oriented Programming Basics/245. Intro to Object Oriented Programming\|245. Intro to Object Oriented Programming]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 29 - BONUS SECTION
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 29 - BONUS SECTION | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 29 - BONUS SECTION/251. Congratulations\|251. Congratulations]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 3 - Working with Text Files In Python
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 3 - Working with Text Files In Python | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 3 - Working with Text Files In Python/26. Intro\|26. Intro]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 4 - Hands-On Challenges - Working With Files
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 4 - Hands-On Challenges - Working With Files | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 4 - Hands-On Challenges - Working With Files/42. Hands-On Challenges - Working with Text Files\|42. Hands-On Challenges - Working with Text Files]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 5 - Data Serialization and Deserialization In Python (Pickle and...)
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 5 - Data Serialization and Deserialization In Python (Pickle and...) | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 5 - Data Serialization and Deserialization In Python (Pickle and...)/44. Intro to Data Serialization\|44. Intro to Data Serialization]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 6 - Network Automation with Paramiko (SSH)
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 6 - Network Automation with Paramiko (SSH) | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 6 - Network Automation with Paramiko (SSH)/56. The Lab Environment\|56. The Lab Environment]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 7 - Hands-On Challenges - Network Automation with Paramiko
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 7 - Hands-On Challenges - Network Automation with Paramiko | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 7 - Hands-On Challenges - Network Automation with Paramiko/76. Hands-On Challenges - Paramiko\|76. Hands-On Challenges - Paramiko]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 8 - Network Automation with Netmiko (SSH)
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 8 - Network Automation with Netmiko (SSH) | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 8 - Network Automation with Netmiko (SSH)/77. The Lab Environment\|77. The Lab Environment]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 9 - Hands-On Challenges - Network Automation with Netmiko
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 9 - Hands-On Challenges - Network Automation with Netmiko | [[Learning/Programming/Python/Automating networks/Master Network Automation with Python for Network Engineers/Section 9 - Hands-On Challenges - Network Automation with Netmiko/93. Hands-On Challenges - Netmiko\|93. Hands-On Challenges - Netmiko]] |
> > > > > 
> > > 
> > > > [!g-white]- Mastering Python Networking
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Mastering Python Networking | [[Learning/Programming/Python/Automating networks/Mastering Python Networking/Mastering Python Networking\|Mastering Python Networking]] |
> > > > | Section 1 - Python Network Programming | [[Learning/Programming/Python/Automating networks/Mastering Python Networking/Section 1 - Python Network Programming/1. The Course Overview\|1. The Course Overview]] |
> > > > | Section 2 - Hands-on Network Programming with Python | [[Learning/Programming/Python/Automating networks/Mastering Python Networking/Section 2 - Hands-on Network Programming with Python/20. The Course Overview\|20. The Course Overview]] |
> > > > 
> > > > > [!g-white]- Section 1 - Python Network Programming
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 1 - Python Network Programming | [[Learning/Programming/Python/Automating networks/Mastering Python Networking/Section 1 - Python Network Programming/1. The Course Overview\|1. The Course Overview]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 2 - Hands-on Network Programming with Python
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 2 - Hands-on Network Programming with Python | [[Learning/Programming/Python/Automating networks/Mastering Python Networking/Section 2 - Hands-on Network Programming with Python/20. The Course Overview\|20. The Course Overview]] |
> > > > > 
> > > 
> > > > [!g-white]- Python Programming for Network Engineers - Cisco, Netmiko ++
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Python Programming for Network Engineers - Cisco, Netmiko ++ | [[Learning/Programming/Python/Automating networks/Python Programming for Network Engineers - Cisco, Netmiko ++/Python Programming for Network Engineers - Cisco, Netmiko ++\|Python Programming for Network Engineers - Cisco, Netmiko ++]] |
> > > > | Section 1 - Introduction | [[Learning/Programming/Python/Automating networks/Python Programming for Network Engineers - Cisco, Netmiko ++/Section 1 - Introduction/1.  Good news!\|1.  Good news!]] |
> > > > | Section 2 - GNS3 Setup | [[Learning/Programming/Python/Automating networks/Python Programming for Network Engineers - Cisco, Netmiko ++/Section 2 - GNS3 Setup/10. EVE-NG Cisco Images\|10. EVE-NG Cisco Images]] |
> > > > | Section 3 - Network Programmability with Python | [[Learning/Programming/Python/Automating networks/Python Programming for Network Engineers - Cisco, Netmiko ++/Section 3 - Network Programmability with Python/12. (Part 1) Network programmability made easy.\|12. (Part 1) Network programmability made easy.]] |
> > > > | Section 4 - Network Automation Appliance | [[Learning/Programming/Python/Automating networks/Python Programming for Network Engineers - Cisco, Netmiko ++/Section 4 - Network Automation Appliance/30. GNS3 Automation Container import and testing Part 1\|30. GNS3 Automation Container import and testing Part 1]] |
> > > > 
> > > > > [!g-white]- Section 1 - Introduction
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 1 - Introduction | [[Learning/Programming/Python/Automating networks/Python Programming for Network Engineers - Cisco, Netmiko ++/Section 1 - Introduction/1.  Good news!\|1.  Good news!]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 2 - GNS3 Setup
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 2 - GNS3 Setup | [[Learning/Programming/Python/Automating networks/Python Programming for Network Engineers - Cisco, Netmiko ++/Section 2 - GNS3 Setup/10. EVE-NG Cisco Images\|10. EVE-NG Cisco Images]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 3 - Network Programmability with Python
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 3 - Network Programmability with Python | [[Learning/Programming/Python/Automating networks/Python Programming for Network Engineers - Cisco, Netmiko ++/Section 3 - Network Programmability with Python/12. (Part 1) Network programmability made easy.\|12. (Part 1) Network programmability made easy.]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 4 - Network Automation Appliance
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 4 - Network Automation Appliance | [[Learning/Programming/Python/Automating networks/Python Programming for Network Engineers - Cisco, Netmiko ++/Section 4 - Network Automation Appliance/30. GNS3 Automation Container import and testing Part 1\|30. GNS3 Automation Container import and testing Part 1]] |
> > > > > 
> > 
> > > [!g-white]- Certification
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | Certification | [[Learning/Programming/Python/Certification/Certification\|Certification]] |
> > > 
> > 
> > > [!g-white]- chatGPT
> > > 
> > > 
> > > > [!g-white]- unit testing
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | unit testing | [[Learning/Programming/Python/chatGPT/unit testing/Untitled\|Untitled]] |
> > > > 
> > 
> > > [!g-white]- Concurrent and Parallel Programming in Python
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | Concurrent and Parallel Programming in Python | [[Learning/Programming/Python/Concurrent and Parallel Programming in Python/Concurrent and Parallel Programming in Python\|Concurrent and Parallel Programming in Python]] |
> > > | Extra info | [[Learning/Programming/Python/Concurrent and Parallel Programming in Python/Extra info/Process vs Thread\|Process vs Thread]] |
> > > | Section 1 - Threading | [[Learning/Programming/Python/Concurrent and Parallel Programming in Python/Section 1 - Threading/1. Threading, Multiprocessing, Async Intro\|1. Threading, Multiprocessing, Async Intro]] |
> > > | Section 1 - Threading (Copy) | [[Learning/Programming/Python/Concurrent and Parallel Programming in Python/Section 1 - Threading (Copy)/1. Threading, Multiprocessing, Async Intro\|1. Threading, Multiprocessing, Async Intro]] |
> > > | Section 2 - Multiprocessing | [[Learning/Programming/Python/Concurrent and Parallel Programming in Python/Section 2 - Multiprocessing/15. Multiprocessing Intro\|15. Multiprocessing Intro]] |
> > > | Section 3 - Asynchronous | [[Learning/Programming/Python/Concurrent and Parallel Programming in Python/Section 3 - Asynchronous/21. Intro to Writing Asynchronous Programs\|21. Intro to Writing Asynchronous Programs]] |
> > > 
> > > > [!g-white]- Extra info
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Extra info | [[Learning/Programming/Python/Concurrent and Parallel Programming in Python/Extra info/Process vs Thread\|Process vs Thread]] |
> > > > 
> > > 
> > > > [!g-white]- Section 1 - Threading
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 1 - Threading | [[Learning/Programming/Python/Concurrent and Parallel Programming in Python/Section 1 - Threading/1. Threading, Multiprocessing, Async Intro\|1. Threading, Multiprocessing, Async Intro]] |
> > > > 
> > > 
> > > > [!g-white]- Section 1 - Threading (Copy)
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 1 - Threading (Copy) | [[Learning/Programming/Python/Concurrent and Parallel Programming in Python/Section 1 - Threading (Copy)/1. Threading, Multiprocessing, Async Intro\|1. Threading, Multiprocessing, Async Intro]] |
> > > > 
> > > 
> > > > [!g-white]- Section 2 - Multiprocessing
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 2 - Multiprocessing | [[Learning/Programming/Python/Concurrent and Parallel Programming in Python/Section 2 - Multiprocessing/15. Multiprocessing Intro\|15. Multiprocessing Intro]] |
> > > > 
> > > 
> > > > [!g-white]- Section 3 - Asynchronous
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 3 - Asynchronous | [[Learning/Programming/Python/Concurrent and Parallel Programming in Python/Section 3 - Asynchronous/21. Intro to Writing Asynchronous Programs\|21. Intro to Writing Asynchronous Programs]] |
> > > > 
> > 
> > > [!g-white]- Data Visualisation
> > > 
> > > 
> > > > [!g-white]- Data Visualization with Python and Matplotlib
> > > > 
> > > > 
> > > > > [!g-white]- Section 1- Course Introduction
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 1- Course Introduction | [[Learning/Programming/Python/Data Visualisation/Data Visualization with Python and Matplotlib/Section 1- Course Introduction/1. Introduction\|1. Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 2- Different types of basic Matplotlib charts
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 2- Different types of basic Matplotlib charts | [[Learning/Programming/Python/Data Visualisation/Data Visualization with Python and Matplotlib/Section 2- Different types of basic Matplotlib charts/10. Stack Plots\|10. Stack Plots]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 3- Basic customization options
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 3- Basic customization options | [[Learning/Programming/Python/Data Visualisation/Data Visualization with Python and Matplotlib/Section 3- Basic customization options/15. Section Intro\|15. Section Intro]] |
> > > > > 
> > > 
> > > > [!g-white]- Plotly
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Plotly | [[Learning/Programming/Python/Data Visualisation/Plotly/Topics\|Topics]] |
> > > > | 1. Getting_Started | [[Learning/Programming/Python/Data Visualisation/Plotly/1. Getting_Started/First_Plot_with_Plotly\|First_Plot_with_Plotly]] |
> > > > | 2. Basic_Plots | [[Learning/Programming/Python/Data Visualisation/Plotly/2. Basic_Plots/Scatter_Plots\|Scatter_Plots]] |
> > > > | 3. Customization | [[Learning/Programming/Python/Data Visualisation/Plotly/3. Customization/Annotations_and_Text\|Annotations_and_Text]] |
> > > > 
> > > > > [!g-white]- 1. Getting_Started
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | 1. Getting_Started | [[Learning/Programming/Python/Data Visualisation/Plotly/1. Getting_Started/First_Plot_with_Plotly\|First_Plot_with_Plotly]] |
> > > > > 
> > > > 
> > > > > [!g-white]- 2. Basic_Plots
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | 2. Basic_Plots | [[Learning/Programming/Python/Data Visualisation/Plotly/2. Basic_Plots/Scatter_Plots\|Scatter_Plots]] |
> > > > > 
> > > > 
> > > > > [!g-white]- 3. Customization
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | 3. Customization | [[Learning/Programming/Python/Data Visualisation/Plotly/3. Customization/Annotations_and_Text\|Annotations_and_Text]] |
> > > > > 
> > > 
> > > > [!g-white]- Python Data Visualization - Matplotlib & Seaborn Masterclass
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Python Data Visualization - Matplotlib & Seaborn Masterclass | [[Learning/Programming/Python/Data Visualisation/Python Data Visualization - Matplotlib & Seaborn Masterclass/Untitled\|Untitled]] |
> > > > | Section 1 - Getting Started | [[Learning/Programming/Python/Data Visualisation/Python Data Visualization - Matplotlib & Seaborn Masterclass/Section 1 - Getting Started/1. Course Structure & Outline\|1. Course Structure & Outline]] |
> > > > | Section 2 - Intro to Data Visualisation | [[Learning/Programming/Python/Data Visualisation/Python Data Visualization - Matplotlib & Seaborn Masterclass/Section 2 - Intro to Data Visualisation/10. Chart Formatting & Storytelling\|10. Chart Formatting & Storytelling]] |
> > > > | Section 3 - Matplotlib Fundamentals | [[Learning/Programming/Python/Data Visualisation/Python Data Visualization - Matplotlib & Seaborn Masterclass/Section 3 - Matplotlib Fundamentals/13. Intro to Matplotlib\|13. Intro to Matplotlib]] |
> > > > | Section 4 - PROJECT 1 Analyzing the Global Coffee Market | [[Learning/Programming/Python/Data Visualisation/Python Data Visualization - Matplotlib & Seaborn Masterclass/Section 4 - PROJECT 1 Analyzing the Global Coffee Market/52. Project 1 Introduction\|52. Project 1 Introduction]] |
> > > > | Section 5 - Advanced Customization | [[Learning/Programming/Python/Data Visualisation/Python Data Visualization - Matplotlib & Seaborn Masterclass/Section 5 - Advanced Customization/54. Intro to Advanced Customization\|54. Intro to Advanced Customization]] |
> > > > | Section 6 - PROJECT 2 Visualizing Global Coffee Production | [[Learning/Programming/Python/Data Visualisation/Python Data Visualization - Matplotlib & Seaborn Masterclass/Section 6 - PROJECT 2 Visualizing Global Coffee Production/71. Project 2 Introduction\|71. Project 2 Introduction]] |
> > > > | Section 7 - Visualization with Seaborn | [[Learning/Programming/Python/Data Visualisation/Python Data Visualization - Matplotlib & Seaborn Masterclass/Section 7 - Visualization with Seaborn/73. Intro to Seaborn\|73. Intro to Seaborn]] |
> > > > | Section 8 - PROJECT 3 Analyzing Used Car Sales | [[Learning/Programming/Python/Data Visualisation/Python Data Visualization - Matplotlib & Seaborn Masterclass/Section 8 - PROJECT 3 Analyzing Used Car Sales/92. Project 3 Introduction\|92. Project 3 Introduction]] |
> > > > | Section 9 - BONUS LESSON | [[Learning/Programming/Python/Data Visualisation/Python Data Visualization - Matplotlib & Seaborn Masterclass/Section 9 - BONUS LESSON/94. BONUS LESSON\|94. BONUS LESSON]] |
> > > > 
> > > > > [!g-white]- Section 1 - Getting Started
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 1 - Getting Started | [[Learning/Programming/Python/Data Visualisation/Python Data Visualization - Matplotlib & Seaborn Masterclass/Section 1 - Getting Started/1. Course Structure & Outline\|1. Course Structure & Outline]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 2 - Intro to Data Visualisation
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 2 - Intro to Data Visualisation | [[Learning/Programming/Python/Data Visualisation/Python Data Visualization - Matplotlib & Seaborn Masterclass/Section 2 - Intro to Data Visualisation/10. Chart Formatting & Storytelling\|10. Chart Formatting & Storytelling]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 3 - Matplotlib Fundamentals
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 3 - Matplotlib Fundamentals | [[Learning/Programming/Python/Data Visualisation/Python Data Visualization - Matplotlib & Seaborn Masterclass/Section 3 - Matplotlib Fundamentals/13. Intro to Matplotlib\|13. Intro to Matplotlib]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 4 - PROJECT 1 Analyzing the Global Coffee Market
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 4 - PROJECT 1 Analyzing the Global Coffee Market | [[Learning/Programming/Python/Data Visualisation/Python Data Visualization - Matplotlib & Seaborn Masterclass/Section 4 - PROJECT 1 Analyzing the Global Coffee Market/52. Project 1 Introduction\|52. Project 1 Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 5 - Advanced Customization
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 5 - Advanced Customization | [[Learning/Programming/Python/Data Visualisation/Python Data Visualization - Matplotlib & Seaborn Masterclass/Section 5 - Advanced Customization/54. Intro to Advanced Customization\|54. Intro to Advanced Customization]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 6 - PROJECT 2 Visualizing Global Coffee Production
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 6 - PROJECT 2 Visualizing Global Coffee Production | [[Learning/Programming/Python/Data Visualisation/Python Data Visualization - Matplotlib & Seaborn Masterclass/Section 6 - PROJECT 2 Visualizing Global Coffee Production/71. Project 2 Introduction\|71. Project 2 Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 7 - Visualization with Seaborn
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 7 - Visualization with Seaborn | [[Learning/Programming/Python/Data Visualisation/Python Data Visualization - Matplotlib & Seaborn Masterclass/Section 7 - Visualization with Seaborn/73. Intro to Seaborn\|73. Intro to Seaborn]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 8 - PROJECT 3 Analyzing Used Car Sales
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 8 - PROJECT 3 Analyzing Used Car Sales | [[Learning/Programming/Python/Data Visualisation/Python Data Visualization - Matplotlib & Seaborn Masterclass/Section 8 - PROJECT 3 Analyzing Used Car Sales/92. Project 3 Introduction\|92. Project 3 Introduction]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 9 - BONUS LESSON
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 9 - BONUS LESSON | [[Learning/Programming/Python/Data Visualisation/Python Data Visualization - Matplotlib & Seaborn Masterclass/Section 9 - BONUS LESSON/94. BONUS LESSON\|94. BONUS LESSON]] |
> > > > > 
> > 
> > > [!g-white]- Design patterns
> > > 
> > > 
> > > > [!g-white]- Design Patterns in Python
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Design Patterns in Python | [[Learning/Programming/Python/Design patterns/Design Patterns in Python/Design Patterns in Python\|Design Patterns in Python]] |
> > > > | Section 1 - Introduction | [[Learning/Programming/Python/Design patterns/Design Patterns in Python/Section 1 - Introduction/1. Environment Setup\|1. Environment Setup]] |
> > > > | Section 2 - Creational Design Patterns | [[Learning/Programming/Python/Design patterns/Design Patterns in Python/Section 2 - Creational Design Patterns/10. Builder\|10. Builder]] |
> > > > | Section 3 - Structural Design Patterns | [[Learning/Programming/Python/Design patterns/Design Patterns in Python/Section 3 - Structural Design Patterns/19. Decorator\|19. Decorator]] |
> > > > | Section 4 - Behavioural Design Patterns | [[Learning/Programming/Python/Design patterns/Design Patterns in Python/Section 4 - Behavioural Design Patterns/45. Command\|45. Command]] |
> > > > | Section 5 - Summary | [[Learning/Programming/Python/Design patterns/Design Patterns in Python/Section 5 - Summary/78. Summary\|78. Summary]] |
> > > > 
> > > > > [!g-white]- Section 1 - Introduction
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 1 - Introduction | [[Learning/Programming/Python/Design patterns/Design Patterns in Python/Section 1 - Introduction/1. Environment Setup\|1. Environment Setup]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 2 - Creational Design Patterns
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 2 - Creational Design Patterns | [[Learning/Programming/Python/Design patterns/Design Patterns in Python/Section 2 - Creational Design Patterns/10. Builder\|10. Builder]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 3 - Structural Design Patterns
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 3 - Structural Design Patterns | [[Learning/Programming/Python/Design patterns/Design Patterns in Python/Section 3 - Structural Design Patterns/19. Decorator\|19. Decorator]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 4 - Behavioural Design Patterns
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 4 - Behavioural Design Patterns | [[Learning/Programming/Python/Design patterns/Design Patterns in Python/Section 4 - Behavioural Design Patterns/45. Command\|45. Command]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 5 - Summary
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 5 - Summary | [[Learning/Programming/Python/Design patterns/Design Patterns in Python/Section 5 - Summary/78. Summary\|78. Summary]] |
> > > > > 
> > 
> > > [!g-white]- Exploratory Data Analysis
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | Exploratory Data Analysis | [[Learning/Programming/Python/Exploratory Data Analysis/EDA\|EDA]] |
> > > 
> > 
> > > [!g-white]- FastAPI
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | FastAPI | [[Learning/Programming/Python/FastAPI/FastAPI\|FastAPI]] |
> > > | Section 1 - Introduction | [[Learning/Programming/Python/FastAPI/Section 1 - Introduction/1. Introduction\|1. Introduction]] |
> > > | Section 10 - Authentication & Authorization | [[Learning/Programming/Python/FastAPI/Section 10 - Authentication & Authorization/116. FastAPI Project - Starting Authentication & Authorization\|116. FastAPI Project - Starting Authentication & Authorization]] |
> > > | Section 11 - Authenticate Requests | [[Learning/Programming/Python/FastAPI/Section 11 - Authenticate Requests/130. FastAPI Project - Post Todo - User ID\|130. FastAPI Project - Post Todo - User ID]] |
> > > | Section 12 - Large Production Database Setup | [[Learning/Programming/Python/FastAPI/Section 12 - Large Production Database Setup/138. FastAPI Project - Production DBMS\|138. FastAPI Project - Production DBMS]] |
> > > | Section 13 - Project 3.5 - Alembic Data Migration | [[Learning/Programming/Python/FastAPI/Section 13 - Project 3.5 - Alembic Data Migration/149. Alembic Data Migration Overview\|149. Alembic Data Migration Overview]] |
> > > | Section 14 - Project 4 - Unit & Integration Testing | [[Learning/Programming/Python/FastAPI/Section 14 - Project 4 - Unit & Integration Testing/157. Testing Overview\|157. Testing Overview]] |
> > > | Section 15 - Project 5 - Full Stack Application | [[Learning/Programming/Python/FastAPI/Section 15 - Project 5 - Full Stack Application/182. Full Stack Introduction\|182. Full Stack Introduction]] |
> > > | Section 16 - Git - Version Control | [[Learning/Programming/Python/FastAPI/Section 16 - Git - Version Control/198. Git Introduction\|198. Git Introduction]] |
> > > | Section 17 - Deploying FastAPI Applications | [[Learning/Programming/Python/FastAPI/Section 17 - Deploying FastAPI Applications/208. Deployment - Render Introduction\|208. Deployment - Render Introduction]] |
> > > | Section 19 - Summary | [[Learning/Programming/Python/FastAPI/Section 19 - Summary/241. Bonus Lecture\|241. Bonus Lecture]] |
> > > | Section 2 - Python Installation and Refresher | [[Learning/Programming/Python/FastAPI/Section 2 - Python Installation and Refresher/10. Python Setup - Mac\|10. Python Setup - Mac]] |
> > > | Section 3 - FastAPI Overview | [[Learning/Programming/Python/FastAPI/Section 3 - FastAPI Overview/61. FastAPI Overview\|61. FastAPI Overview]] |
> > > | Section 4 - FastAPI Setup & Installation | [[Learning/Programming/Python/FastAPI/Section 4 - FastAPI Setup & Installation/62. Virtual Environments Overview\|62. Virtual Environments Overview]] |
> > > | Section 5 - Project 1 - FastAPI Request Method Logic | [[Learning/Programming/Python/FastAPI/Section 5 - Project 1 - FastAPI Request Method Logic/65. Books Project Introduction\|65. Books Project Introduction]] |
> > > | Section 6 - Project 2 - Move Fast with FastAPI | [[Learning/Programming/Python/FastAPI/Section 6 - Project 2 - Move Fast with FastAPI/100. FastAPI Project - Explicit Status Code Responses\|100. FastAPI Project - Explicit Status Code Responses]] |
> > > | Section 7 - Project 3 - Complete RESTFUL APIs | [[Learning/Programming/Python/FastAPI/Section 7 - Project 3 - Complete RESTFUL APIs/101. Project 3 - Overview\|101. Project 3 - Overview]] |
> > > | Section 8 - Setup Database | [[Learning/Programming/Python/FastAPI/Section 8 - Setup Database/103. FastAPI Project - SQL Database Introduction\|103. FastAPI Project - SQL Database Introduction]] |
> > > | Section 9 - API Request Methods | [[Learning/Programming/Python/FastAPI/Section 9 - API Request Methods/111. FastAPI Project - Get All Todos from Database\|111. FastAPI Project - Get All Todos from Database]] |
> > > 
> > > > [!g-white]- Section 1 - Introduction
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 1 - Introduction | [[Learning/Programming/Python/FastAPI/Section 1 - Introduction/1. Introduction\|1. Introduction]] |
> > > > 
> > > 
> > > > [!g-white]- Section 10 - Authentication & Authorization
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 10 - Authentication & Authorization | [[Learning/Programming/Python/FastAPI/Section 10 - Authentication & Authorization/116. FastAPI Project - Starting Authentication & Authorization\|116. FastAPI Project - Starting Authentication & Authorization]] |
> > > > 
> > > 
> > > > [!g-white]- Section 11 - Authenticate Requests
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 11 - Authenticate Requests | [[Learning/Programming/Python/FastAPI/Section 11 - Authenticate Requests/130. FastAPI Project - Post Todo - User ID\|130. FastAPI Project - Post Todo - User ID]] |
> > > > 
> > > 
> > > > [!g-white]- Section 12 - Large Production Database Setup
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 12 - Large Production Database Setup | [[Learning/Programming/Python/FastAPI/Section 12 - Large Production Database Setup/138. FastAPI Project - Production DBMS\|138. FastAPI Project - Production DBMS]] |
> > > > 
> > > 
> > > > [!g-white]- Section 13 - Project 3.5 - Alembic Data Migration
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 13 - Project 3.5 - Alembic Data Migration | [[Learning/Programming/Python/FastAPI/Section 13 - Project 3.5 - Alembic Data Migration/149. Alembic Data Migration Overview\|149. Alembic Data Migration Overview]] |
> > > > 
> > > 
> > > > [!g-white]- Section 14 - Project 4 - Unit & Integration Testing
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 14 - Project 4 - Unit & Integration Testing | [[Learning/Programming/Python/FastAPI/Section 14 - Project 4 - Unit & Integration Testing/157. Testing Overview\|157. Testing Overview]] |
> > > > 
> > > 
> > > > [!g-white]- Section 15 - Project 5 - Full Stack Application
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 15 - Project 5 - Full Stack Application | [[Learning/Programming/Python/FastAPI/Section 15 - Project 5 - Full Stack Application/182. Full Stack Introduction\|182. Full Stack Introduction]] |
> > > > 
> > > 
> > > > [!g-white]- Section 16 - Git - Version Control
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 16 - Git - Version Control | [[Learning/Programming/Python/FastAPI/Section 16 - Git - Version Control/198. Git Introduction\|198. Git Introduction]] |
> > > > 
> > > 
> > > > [!g-white]- Section 17 - Deploying FastAPI Applications
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 17 - Deploying FastAPI Applications | [[Learning/Programming/Python/FastAPI/Section 17 - Deploying FastAPI Applications/208. Deployment - Render Introduction\|208. Deployment - Render Introduction]] |
> > > > 
> > > 
> > > > [!g-white]- Section 19 - Summary
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 19 - Summary | [[Learning/Programming/Python/FastAPI/Section 19 - Summary/241. Bonus Lecture\|241. Bonus Lecture]] |
> > > > 
> > > 
> > > > [!g-white]- Section 2 - Python Installation and Refresher
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 2 - Python Installation and Refresher | [[Learning/Programming/Python/FastAPI/Section 2 - Python Installation and Refresher/10. Python Setup - Mac\|10. Python Setup - Mac]] |
> > > > 
> > > 
> > > > [!g-white]- Section 3 - FastAPI Overview
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 3 - FastAPI Overview | [[Learning/Programming/Python/FastAPI/Section 3 - FastAPI Overview/61. FastAPI Overview\|61. FastAPI Overview]] |
> > > > 
> > > 
> > > > [!g-white]- Section 4 - FastAPI Setup & Installation
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 4 - FastAPI Setup & Installation | [[Learning/Programming/Python/FastAPI/Section 4 - FastAPI Setup & Installation/62. Virtual Environments Overview\|62. Virtual Environments Overview]] |
> > > > 
> > > 
> > > > [!g-white]- Section 5 - Project 1 - FastAPI Request Method Logic
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 5 - Project 1 - FastAPI Request Method Logic | [[Learning/Programming/Python/FastAPI/Section 5 - Project 1 - FastAPI Request Method Logic/65. Books Project Introduction\|65. Books Project Introduction]] |
> > > > 
> > > 
> > > > [!g-white]- Section 6 - Project 2 - Move Fast with FastAPI
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 6 - Project 2 - Move Fast with FastAPI | [[Learning/Programming/Python/FastAPI/Section 6 - Project 2 - Move Fast with FastAPI/100. FastAPI Project - Explicit Status Code Responses\|100. FastAPI Project - Explicit Status Code Responses]] |
> > > > 
> > > 
> > > > [!g-white]- Section 7 - Project 3 - Complete RESTFUL APIs
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 7 - Project 3 - Complete RESTFUL APIs | [[Learning/Programming/Python/FastAPI/Section 7 - Project 3 - Complete RESTFUL APIs/101. Project 3 - Overview\|101. Project 3 - Overview]] |
> > > > 
> > > 
> > > > [!g-white]- Section 8 - Setup Database
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 8 - Setup Database | [[Learning/Programming/Python/FastAPI/Section 8 - Setup Database/103. FastAPI Project - SQL Database Introduction\|103. FastAPI Project - SQL Database Introduction]] |
> > > > 
> > > 
> > > > [!g-white]- Section 9 - API Request Methods
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 9 - API Request Methods | [[Learning/Programming/Python/FastAPI/Section 9 - API Request Methods/111. FastAPI Project - Get All Todos from Database\|111. FastAPI Project - Get All Todos from Database]] |
> > > > 
> > 
> > > [!g-white]- MathByte Academy
> > > 
> > > 
> > > > [!g-white]- Extra info
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Extra info | [[Learning/Programming/Python/MathByte Academy/Extra info/Extra info\|Extra info]] |
> > > > | A Deep Dive into Python's Dataclasses | [[Learning/Programming/Python/MathByte Academy/Extra info/A Deep Dive into Python's Dataclasses/A Deep Dive into Python's Dataclasses (Part 1)\|A Deep Dive into Python's Dataclasses (Part 1)]] |
> > > > | context_with_gil_and_threads(Optional) | [[Learning/Programming/Python/MathByte Academy/Extra info/context_with_gil_and_threads(Optional)/01_gil_basics — What is the GIL and why it exists\|01_gil_basics — What is the GIL and why it exists]] |
> > > > | multiple_inheritance | [[Learning/Programming/Python/MathByte Academy/Extra info/multiple_inheritance/01_multiple_inheritance_intro — Basic syntax and structure\|01_multiple_inheritance_intro — Basic syntax and structure]] |
> > > > | Python Design Patterns | [[Learning/Programming/Python/MathByte Academy/Extra info/Python Design Patterns/Python Design Patterns\|Python Design Patterns]] |
> > > > | Python Logging Demystified | [[Learning/Programming/Python/MathByte Academy/Extra info/Python Logging Demystified/Python Logging Demystified - Part 1 - Concepts\|Python Logging Demystified - Part 1 - Concepts]] |
> > > > | super() | [[Learning/Programming/Python/MathByte Academy/Extra info/super()/01_super_basics — Using super() in single inheritance\|01_super_basics — Using super() in single inheritance]] |
> > > > 
> > > > > [!g-white]- A Deep Dive into Python's Dataclasses
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | A Deep Dive into Python's Dataclasses | [[Learning/Programming/Python/MathByte Academy/Extra info/A Deep Dive into Python's Dataclasses/A Deep Dive into Python's Dataclasses (Part 1)\|A Deep Dive into Python's Dataclasses (Part 1)]] |
> > > > > 
> > > > 
> > > > > [!g-white]- context_with_gil_and_threads(Optional)
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | context_with_gil_and_threads(Optional) | [[Learning/Programming/Python/MathByte Academy/Extra info/context_with_gil_and_threads(Optional)/01_gil_basics — What is the GIL and why it exists\|01_gil_basics — What is the GIL and why it exists]] |
> > > > > 
> > > > 
> > > > > [!g-white]- multiple_inheritance
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | multiple_inheritance | [[Learning/Programming/Python/MathByte Academy/Extra info/multiple_inheritance/01_multiple_inheritance_intro — Basic syntax and structure\|01_multiple_inheritance_intro — Basic syntax and structure]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Python Design Patterns
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Python Design Patterns | [[Learning/Programming/Python/MathByte Academy/Extra info/Python Design Patterns/Python Design Patterns\|Python Design Patterns]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Python Logging Demystified
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Python Logging Demystified | [[Learning/Programming/Python/MathByte Academy/Extra info/Python Logging Demystified/Python Logging Demystified - Part 1 - Concepts\|Python Logging Demystified - Part 1 - Concepts]] |
> > > > > 
> > > > 
> > > > > [!g-white]- super()
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | super() | [[Learning/Programming/Python/MathByte Academy/Extra info/super()/01_super_basics — Using super() in single inheritance\|01_super_basics — Using super() in single inheritance]] |
> > > > > 
> > > 
> > > > [!g-white]- Python 3 Deep Dive
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Python 3 Deep Dive | [[Learning/Programming/Python/MathByte Academy/Python 3 Deep Dive/Python 3 Deep Dive\|Python 3 Deep Dive]] |
> > > > | Pydantic V2 - Essentials | [[Learning/Programming/Python/MathByte Academy/Python 3 Deep Dive/Pydantic V2 - Essentials/Pydantic V2 - Essentials\|Pydantic V2 - Essentials]] |
> > > > | Python 3 Deep Dive (Part 1 - Functional) | [[Learning/Programming/Python/MathByte Academy/Python 3 Deep Dive/Python 3 Deep Dive (Part 1 - Functional)/Python 3 Deep Dive (Part 1 - Functional)\|Python 3 Deep Dive (Part 1 - Functional)]] |
> > > > | Python 3 Deep Dive (Part 4 - OOP) | [[Learning/Programming/Python/MathByte Academy/Python 3 Deep Dive/Python 3 Deep Dive (Part 4 - OOP)/Python 3 Deep Dive (Part 4 - OOP)\|Python 3 Deep Dive (Part 4 - OOP)]] |
> > > > 
> > > > > [!g-white]- Pydantic V2 - Essentials
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Pydantic V2 - Essentials | [[Learning/Programming/Python/MathByte Academy/Python 3 Deep Dive/Pydantic V2 - Essentials/Pydantic V2 - Essentials\|Pydantic V2 - Essentials]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Python 3 Deep Dive (Part 1 - Functional)
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Python 3 Deep Dive (Part 1 - Functional) | [[Learning/Programming/Python/MathByte Academy/Python 3 Deep Dive/Python 3 Deep Dive (Part 1 - Functional)/Python 3 Deep Dive (Part 1 - Functional)\|Python 3 Deep Dive (Part 1 - Functional)]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Python 3 Deep Dive (Part 2 - Iterators, Generators)
> > > > > 
> > > > > 
> > > > 
> > > > > [!g-white]- Python 3 Deep Dive (Part 3 - Dictionaries, Sets, JSON)
> > > > > 
> > > > > 
> > > > 
> > > > > [!g-white]- Python 3 Deep Dive (Part 4 - OOP)
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Python 3 Deep Dive (Part 4 - OOP) | [[Learning/Programming/Python/MathByte Academy/Python 3 Deep Dive/Python 3 Deep Dive (Part 4 - OOP)/Python 3 Deep Dive (Part 4 - OOP)\|Python 3 Deep Dive (Part 4 - OOP)]] |
> > > > > 
> > 
> > > [!g-white]- MCP
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | MCP | [[Learning/Programming/Python/MCP/1-introduction-and-context\|1-introduction-and-context]] |
> > > | coursera - introduction-to-model-context-protocol | [[Learning/Programming/Python/MCP/coursera - introduction-to-model-context-protocol/mnemonics\|mnemonics]] |
> > > | coursera-model-context-protocol-advanced-topics | [[Learning/Programming/Python/MCP/coursera-model-context-protocol-advanced-topics/03_assessment-and-next-steps/quiz\|quiz]] |
> > > | Extra info | [[Learning/Programming/Python/MCP/Extra info/Code used\|Code used]] |
> > > | Udemy - MCP Crash Course  Complete Model Context Protocol in a Day | [[Learning/Programming/Python/MCP/Udemy - MCP Crash Course  Complete Model Context Protocol in a Day/Section 1 - Welcome & Course Overview/1. Course Objectives\|1. Course Objectives]] |
> > > 
> > > > [!g-white]- coursera - introduction-to-model-context-protocol
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | coursera - introduction-to-model-context-protocol | [[Learning/Programming/Python/MCP/coursera - introduction-to-model-context-protocol/mnemonics\|mnemonics]] |
> > > > 
> > > > > [!g-white]- 01_introduction
> > > > > 
> > > > > 
> > > > 
> > > > > [!g-white]- 02_hands-on-with-mcp-servers
> > > > > 
> > > > > 
> > > > 
> > > > > [!g-white]- 03_connecting-with-mcp-clients
> > > > > 
> > > > > 
> > > > 
> > > > > [!g-white]- 04_assessment-and-wrap-up
> > > > > 
> > > > > 
> > > 
> > > > [!g-white]- coursera-model-context-protocol-advanced-topics
> > > > 
> > > > 
> > > > > [!g-white]- 01_core-mcp-features
> > > > > 
> > > > > 
> > > > 
> > > > > [!g-white]- 02_transports-and-communication
> > > > > 
> > > > > 
> > > > 
> > > > > [!g-white]- 03_assessment-and-next-steps
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | 03_assessment-and-next-steps | [[Learning/Programming/Python/MCP/coursera-model-context-protocol-advanced-topics/03_assessment-and-next-steps/quiz\|quiz]] |
> > > > > 
> > > 
> > > > [!g-white]- Extra info
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Extra info | [[Learning/Programming/Python/MCP/Extra info/Code used\|Code used]] |
> > > > 
> > > 
> > > > [!g-white]- Udemy - MCP Crash Course  Complete Model Context Protocol in a Day
> > > > 
> > > > 
> > > > > [!g-white]- Section 1 - Welcome & Course Overview
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 1 - Welcome & Course Overview | [[Learning/Programming/Python/MCP/Udemy - MCP Crash Course  Complete Model Context Protocol in a Day/Section 1 - Welcome & Course Overview/1. Course Objectives\|1. Course Objectives]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 10 - MCP Interview
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 10 - MCP Interview | [[Learning/Programming/Python/MCP/Udemy - MCP Crash Course  Complete Model Context Protocol in a Day/Section 10 - MCP Interview/Role Play 1 - MCP Interview\|Role Play 1 - MCP Interview]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 11 - Agent 2 Agent
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 11 - Agent 2 Agent | [[Learning/Programming/Python/MCP/Udemy - MCP Crash Course  Complete Model Context Protocol in a Day/Section 11 - Agent 2 Agent/71. Introduction to A2A - Agent to Agent Protocol\|71. Introduction to A2A - Agent to Agent Protocol]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 12 - FastMCP 2.0 featuring Jeremaiah Lowin
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 12 - FastMCP 2.0 featuring Jeremaiah Lowin | [[Learning/Programming/Python/MCP/Udemy - MCP Crash Course  Complete Model Context Protocol in a Day/Section 12 - FastMCP 2.0 featuring Jeremaiah Lowin/72. How FastMCP Began- Jeremiah's Journey and the Need for Better MCP Tools\|72. How FastMCP Began- Jeremiah's Journey and the Need for Better MCP Tools]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 13 - Advanced Topics In MCP
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 13 - Advanced Topics In MCP | [[Learning/Programming/Python/MCP/Udemy - MCP Crash Course  Complete Model Context Protocol in a Day/Section 13 - Advanced Topics In MCP/77. Theory Sampling\|77. Theory Sampling]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 14 - Whats Wrong with MCP
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 14 - Whats Wrong with MCP | [[Learning/Programming/Python/MCP/Udemy - MCP Crash Course  Complete Model Context Protocol in a Day/Section 14 - Whats Wrong with MCP/80. The 4 Major Drawbacks of the Model Context Protocol\|80. The 4 Major Drawbacks of the Model Context Protocol]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 15 - Agent Skills
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 15 - Agent Skills | [[Learning/Programming/Python/MCP/Udemy - MCP Crash Course  Complete Model Context Protocol in a Day/Section 15 - Agent Skills/82. Intro\|82. Intro]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 16 - Bonus
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 16 - Bonus | [[Learning/Programming/Python/MCP/Udemy - MCP Crash Course  Complete Model Context Protocol in a Day/Section 16 - Bonus/86. Bonus\|86. Bonus]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 2 - Hello World MCP - Configuring Pre Built MCP Servers with Weather Server
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 2 - Hello World MCP - Configuring Pre Built MCP Servers with Weather Server | [[Learning/Programming/Python/MCP/Udemy - MCP Crash Course  Complete Model Context Protocol in a Day/Section 2 - Hello World MCP - Configuring Pre Built MCP Servers with Weather Server/10. Configure Claude Desktop with a local MCP Server\|10. Configure Claude Desktop with a local MCP Server]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 3 - Model Context Protocol Architecture
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 3 - Model Context Protocol Architecture | [[Learning/Programming/Python/MCP/Udemy - MCP Crash Course  Complete Model Context Protocol in a Day/Section 3 - Model Context Protocol Architecture/15. MCP Architecture Concepts - Hosts, Servers, Clients, and the Protocol\|15. MCP Architecture Concepts - Hosts, Servers, Clients, and the Protocol]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 4 - MCP Servers
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 4 - MCP Servers | [[Learning/Programming/Python/MCP/Udemy - MCP Crash Course  Complete Model Context Protocol in a Day/Section 4 - MCP Servers/18. The Theory of MCP Servers\|18. The Theory of MCP Servers]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 5 - Building, Securing, and Containerizing an MCP Server
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 5 - Building, Securing, and Containerizing an MCP Server | [[Learning/Programming/Python/MCP/Udemy - MCP Crash Course  Complete Model Context Protocol in a Day/Section 5 - Building, Securing, and Containerizing an MCP Server/22. What are we building\|22. What are we building]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 6 - Connecting LLM Clients - Tool Calling Mechanisms and MCP
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 6 - Connecting LLM Clients - Tool Calling Mechanisms and MCP | [[Learning/Programming/Python/MCP/Udemy - MCP Crash Course  Complete Model Context Protocol in a Day/Section 6 - Connecting LLM Clients - Tool Calling Mechanisms and MCP/32. Intro\|32. Intro]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 7 - Prompts and Reources
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 7 - Prompts and Reources | [[Learning/Programming/Python/MCP/Udemy - MCP Crash Course  Complete Model Context Protocol in a Day/Section 7 - Prompts and Reources/42. MCP Prompts and Resources High Level\|42. MCP Prompts and Resources High Level]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 8 - I LOVE SSE Servers
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 8 - I LOVE SSE Servers | [[Learning/Programming/Python/MCP/Udemy - MCP Crash Course  Complete Model Context Protocol in a Day/Section 8 - I LOVE SSE Servers/50. intro\|50. intro]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 9 - Secure, Cloud native MCP Servers- Auth0 + Cloudflare Workers
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 9 - Secure, Cloud native MCP Servers- Auth0 + Cloudflare Workers | [[Learning/Programming/Python/MCP/Udemy - MCP Crash Course  Complete Model Context Protocol in a Day/Section 9 - Secure, Cloud native MCP Servers- Auth0 + Cloudflare Workers/55. Introduction- How to Bridge Local AI Apps and Secure Cloud APIs with MCP Servers\|55. Introduction- How to Bridge Local AI Apps and Secure Cloud APIs with MCP Servers]] |
> > > > > 
> > 
> > > [!g-white]- Numpy
> > > 
> > > 
> > > > [!g-white]- Preprocessing Data with NumPy
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Preprocessing Data with NumPy | [[Learning/Programming/Python/Numpy/Preprocessing Data with NumPy/Untitled\|Untitled]] |
> > > > | Section 1 - Introduction to NumPy | [[Learning/Programming/Python/Numpy/Preprocessing Data with NumPy/Section 1 - Introduction to NumPy/1. What Does the Course Cover MOC\|1. What Does the Course Cover MOC]] |
> > > > | Section 2 - Why Do We Use NumPy | [[Learning/Programming/Python/Numpy/Preprocessing Data with NumPy/Section 2 - Why Do We Use NumPy/10. ndarrays\|10. ndarrays]] |
> > > > | Section 3 - NumPy Fundamentals | [[Learning/Programming/Python/Numpy/Preprocessing Data with NumPy/Section 3 - NumPy Fundamentals/13. Indexing\|13. Indexing]] |
> > > > | Section 4 - Working with Arrays | [[Learning/Programming/Python/Numpy/Preprocessing Data with NumPy/Section 4 - Working with Arrays/20. Basic Slicing\|20. Basic Slicing]] |
> > > > | Section 5 - Generating Data with NumPy | [[Learning/Programming/Python/Numpy/Preprocessing Data with NumPy/Section 5 - Generating Data with NumPy/25. Empty Arrays, Arrays of Identical Values\|25. Empty Arrays, Arrays of Identical Values]] |
> > > > | Section 6 - Importing and Saving Data | [[Learning/Programming/Python/Numpy/Preprocessing Data with NumPy/Section 6 - Importing and Saving Data/33. Importing Data with Numpy - np.loadtxt() vs np.genfromtxt()\|33. Importing Data with Numpy - np.loadtxt() vs np.genfromtxt()]] |
> > > > | Section 7 - Statistics with NumPy | [[Learning/Programming/Python/Numpy/Preprocessing Data with NumPy/Section 7 - Statistics with NumPy/41. Using NumPy Statistical Functions\|41. Using NumPy Statistical Functions]] |
> > > > | Section 8 - Manipulating Data with NumPy | [[Learning/Programming/Python/Numpy/Preprocessing Data with NumPy/Section 8 - Manipulating Data with NumPy/50. Checking for Missing Values\|50. Checking for Missing Values]] |
> > > > | Section 9 - A NumPy Practical Example | [[Learning/Programming/Python/Numpy/Preprocessing Data with NumPy/Section 9 - A NumPy Practical Example/63. Setting Up - Introduction to the Practical Example\|63. Setting Up - Introduction to the Practical Example]] |
> > > > 
> > > > > [!g-white]- Section 1 - Introduction to NumPy
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 1 - Introduction to NumPy | [[Learning/Programming/Python/Numpy/Preprocessing Data with NumPy/Section 1 - Introduction to NumPy/1. What Does the Course Cover MOC\|1. What Does the Course Cover MOC]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 2 - Why Do We Use NumPy
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 2 - Why Do We Use NumPy | [[Learning/Programming/Python/Numpy/Preprocessing Data with NumPy/Section 2 - Why Do We Use NumPy/10. ndarrays\|10. ndarrays]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 3 - NumPy Fundamentals
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 3 - NumPy Fundamentals | [[Learning/Programming/Python/Numpy/Preprocessing Data with NumPy/Section 3 - NumPy Fundamentals/13. Indexing\|13. Indexing]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 4 - Working with Arrays
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 4 - Working with Arrays | [[Learning/Programming/Python/Numpy/Preprocessing Data with NumPy/Section 4 - Working with Arrays/20. Basic Slicing\|20. Basic Slicing]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 5 - Generating Data with NumPy
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 5 - Generating Data with NumPy | [[Learning/Programming/Python/Numpy/Preprocessing Data with NumPy/Section 5 - Generating Data with NumPy/25. Empty Arrays, Arrays of Identical Values\|25. Empty Arrays, Arrays of Identical Values]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 6 - Importing and Saving Data
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 6 - Importing and Saving Data | [[Learning/Programming/Python/Numpy/Preprocessing Data with NumPy/Section 6 - Importing and Saving Data/33. Importing Data with Numpy - np.loadtxt() vs np.genfromtxt()\|33. Importing Data with Numpy - np.loadtxt() vs np.genfromtxt()]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 7 - Statistics with NumPy
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 7 - Statistics with NumPy | [[Learning/Programming/Python/Numpy/Preprocessing Data with NumPy/Section 7 - Statistics with NumPy/41. Using NumPy Statistical Functions\|41. Using NumPy Statistical Functions]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 8 - Manipulating Data with NumPy
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 8 - Manipulating Data with NumPy | [[Learning/Programming/Python/Numpy/Preprocessing Data with NumPy/Section 8 - Manipulating Data with NumPy/50. Checking for Missing Values\|50. Checking for Missing Values]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 9 - A NumPy Practical Example
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 9 - A NumPy Practical Example | [[Learning/Programming/Python/Numpy/Preprocessing Data with NumPy/Section 9 - A NumPy Practical Example/63. Setting Up - Introduction to the Practical Example\|63. Setting Up - Introduction to the Practical Example]] |
> > > > > 
> > > 
> > > > [!g-white]- Udemy - Intro to NumPy
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Udemy - Intro to NumPy | [[Learning/Programming/Python/Numpy/Udemy - Intro to NumPy/1. Overview\|1. Overview]] |
> > > > 
> > 
> > > [!g-white]- Pandas
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | Pandas | [[Learning/Programming/Python/Pandas/Pandas\|Pandas]] |
> > > | Data Representation files | [[Learning/Programming/Python/Pandas/Data Representation files/customers.head()\|customers.head()]] |
> > > | Extrainfo | [[Learning/Programming/Python/Pandas/Extrainfo/0000Extra info\|0000Extra info]] |
> > > | Section 1 - Installation and Setup | [[Learning/Programming/Python/Pandas/Section 1 - Installation and Setup/1. Introduction to the Course\|1. Introduction to the Course]] |
> > > | Section 10 - Merging, Joining, and Concatenating DataFrames | [[Learning/Programming/Python/Pandas/Section 10 - Merging, Joining, and Concatenating DataFrames/107. Intro to the Merging DataFrames Module\|107. Intro to the Merging DataFrames Module]] |
> > > | Section 11 - Working with Dates and Times in Datasets | [[Learning/Programming/Python/Pandas/Section 11 - Working with Dates and Times in Datasets/117. Intro to the Working with Dates and Times Module and Review of Python's datetime\|117. Intro to the Working with Dates and Times Module and Review of Python's datetime]] |
> > > | Section 12 - Input and Output in pandas | [[Learning/Programming/Python/Pandas/Section 12 - Input and Output in pandas/125. URL for Next Lesson's Dataset\|125. URL for Next Lesson's Dataset]] |
> > > | Section 13 - Visualization | [[Learning/Programming/Python/Pandas/Section 13 - Visualization/131. Install matplotlib Library for Visualization\|131. Install matplotlib Library for Visualization]] |
> > > | Section 14 - Options and Settings in pandas | [[Learning/Programming/Python/Pandas/Section 14 - Options and Settings in pandas/202. Introduction to the Options and Settings Module\|202. Introduction to the Options and Settings Module]] |
> > > | Section 2 - Python Crash Course | [[Learning/Programming/Python/Pandas/Section 2 - Python Crash Course/Section 2 - Python Crash Course\|Section 2 - Python Crash Course]] |
> > > | Section 3 - Series | [[Learning/Programming/Python/Pandas/Section 3 - Series/23. Create a Series Object from a List\|23. Create a Series Object from a List]] |
> > > | Section 4 - DataFrames I Introduction | [[Learning/Programming/Python/Pandas/Section 4 - DataFrames I Introduction/44. Methods and Attributes between Series and DataFrames\|44. Methods and Attributes between Series and DataFrames]] |
> > > | Section 5 - DataFrames II Filtering Data | [[Learning/Programming/Python/Pandas/Section 5 - DataFrames II Filtering Data/100. Coding Exercise Solution - Filter DataFrame with More than One Condition (OR)\|100. Coding Exercise Solution - Filter DataFrame with More than One Condition (OR)]] |
> > > | Section 6 - DataFrames III Data Extraction | [[Learning/Programming/Python/Pandas/Section 6 - DataFrames III Data Extraction/68. This Module's Dataset\|68. This Module's Dataset]] |
> > > | Section 7 - Working with Text Data | [[Learning/Programming/Python/Pandas/Section 7 - Working with Text Data/81. This Module's Dataset\|81. This Module's Dataset]] |
> > > | Section 8 - MultiIndex | [[Learning/Programming/Python/Pandas/Section 8 - MultiIndex/88. Intro to the MultiIndex Module\|88. Intro to the MultiIndex Module]] |
> > > | Section 9 - The GroupBy Object | [[Learning/Programming/Python/Pandas/Section 9 - The GroupBy Object/100. Intro to the GroupBy Module\|100. Intro to the GroupBy Module]] |
> > > 
> > > > [!g-white]- Data Representation files
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Data Representation files | [[Learning/Programming/Python/Pandas/Data Representation files/customers.head()\|customers.head()]] |
> > > > 
> > > 
> > > > [!g-white]- Extrainfo
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Extrainfo | [[Learning/Programming/Python/Pandas/Extrainfo/0000Extra info\|0000Extra info]] |
> > > > 
> > > 
> > > > [!g-white]- Section 1 - Installation and Setup
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 1 - Installation and Setup | [[Learning/Programming/Python/Pandas/Section 1 - Installation and Setup/1. Introduction to the Course\|1. Introduction to the Course]] |
> > > > 
> > > 
> > > > [!g-white]- Section 10 - Merging, Joining, and Concatenating DataFrames
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 10 - Merging, Joining, and Concatenating DataFrames | [[Learning/Programming/Python/Pandas/Section 10 - Merging, Joining, and Concatenating DataFrames/107. Intro to the Merging DataFrames Module\|107. Intro to the Merging DataFrames Module]] |
> > > > 
> > > 
> > > > [!g-white]- Section 11 - Working with Dates and Times in Datasets
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 11 - Working with Dates and Times in Datasets | [[Learning/Programming/Python/Pandas/Section 11 - Working with Dates and Times in Datasets/117. Intro to the Working with Dates and Times Module and Review of Python's datetime\|117. Intro to the Working with Dates and Times Module and Review of Python's datetime]] |
> > > > 
> > > 
> > > > [!g-white]- Section 12 - Input and Output in pandas
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 12 - Input and Output in pandas | [[Learning/Programming/Python/Pandas/Section 12 - Input and Output in pandas/125. URL for Next Lesson's Dataset\|125. URL for Next Lesson's Dataset]] |
> > > > 
> > > 
> > > > [!g-white]- Section 13 - Visualization
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 13 - Visualization | [[Learning/Programming/Python/Pandas/Section 13 - Visualization/131. Install matplotlib Library for Visualization\|131. Install matplotlib Library for Visualization]] |
> > > > 
> > > 
> > > > [!g-white]- Section 14 - Options and Settings in pandas
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 14 - Options and Settings in pandas | [[Learning/Programming/Python/Pandas/Section 14 - Options and Settings in pandas/202. Introduction to the Options and Settings Module\|202. Introduction to the Options and Settings Module]] |
> > > > 
> > > 
> > > > [!g-white]- Section 2 - Python Crash Course
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 2 - Python Crash Course | [[Learning/Programming/Python/Pandas/Section 2 - Python Crash Course/Section 2 - Python Crash Course\|Section 2 - Python Crash Course]] |
> > > > 
> > > 
> > > > [!g-white]- Section 3 - Series
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 3 - Series | [[Learning/Programming/Python/Pandas/Section 3 - Series/23. Create a Series Object from a List\|23. Create a Series Object from a List]] |
> > > > 
> > > 
> > > > [!g-white]- Section 4 - DataFrames I Introduction
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 4 - DataFrames I Introduction | [[Learning/Programming/Python/Pandas/Section 4 - DataFrames I Introduction/44. Methods and Attributes between Series and DataFrames\|44. Methods and Attributes between Series and DataFrames]] |
> > > > 
> > > 
> > > > [!g-white]- Section 5 - DataFrames II Filtering Data
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 5 - DataFrames II Filtering Data | [[Learning/Programming/Python/Pandas/Section 5 - DataFrames II Filtering Data/100. Coding Exercise Solution - Filter DataFrame with More than One Condition (OR)\|100. Coding Exercise Solution - Filter DataFrame with More than One Condition (OR)]] |
> > > > 
> > > 
> > > > [!g-white]- Section 6 - DataFrames III Data Extraction
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 6 - DataFrames III Data Extraction | [[Learning/Programming/Python/Pandas/Section 6 - DataFrames III Data Extraction/68. This Module's Dataset\|68. This Module's Dataset]] |
> > > > 
> > > 
> > > > [!g-white]- Section 7 - Working with Text Data
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 7 - Working with Text Data | [[Learning/Programming/Python/Pandas/Section 7 - Working with Text Data/81. This Module's Dataset\|81. This Module's Dataset]] |
> > > > 
> > > 
> > > > [!g-white]- Section 8 - MultiIndex
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 8 - MultiIndex | [[Learning/Programming/Python/Pandas/Section 8 - MultiIndex/88. Intro to the MultiIndex Module\|88. Intro to the MultiIndex Module]] |
> > > > 
> > > 
> > > > [!g-white]- Section 9 - The GroupBy Object
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Section 9 - The GroupBy Object | [[Learning/Programming/Python/Pandas/Section 9 - The GroupBy Object/100. Intro to the GroupBy Module\|100. Intro to the GroupBy Module]] |
> > > > 
> > 
> > > [!g-white]- Plotly_Dash
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | Plotly_Dash | [[Learning/Programming/Python/Plotly_Dash/1. Course Overview\|1. Course Overview]] |
> > > 
> > 
> > > [!g-white]- Practice
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | Practice | [[Learning/Programming/Python/Practice/Practice\|Practice]] |
> > > | Interview questions | [[Learning/Programming/Python/Practice/Interview questions/!r and !s\|!r and !s]] |
> > > | Practice questions | [[Learning/Programming/Python/Practice/Practice questions/1. re, os.scandir, Path, sets, exceptions\|1. re, os.scandir, Path, sets, exceptions]] |
> > > | udemy | [[Learning/Programming/Python/Practice/udemy/210+ Exercises - Python Standard Libraries/210+ Exercises - Python Standard Libraries\|210+ Exercises - Python Standard Libraries]] |
> > > 
> > > > [!g-white]- Interview questions
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Interview questions | [[Learning/Programming/Python/Practice/Interview questions/!r and !s\|!r and !s]] |
> > > > | BOA | [[Learning/Programming/Python/Practice/Interview questions/BOA/CE questions\|CE questions]] |
> > > > | practice problems | [[Learning/Programming/Python/Practice/Interview questions/practice problems/Instance Methods, Class Methods, Static Methods and Alternative Constructors practice\|Instance Methods, Class Methods, Static Methods and Alternative Constructors practice]] |
> > > > 
> > > > > [!g-white]- BOA
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | BOA | [[Learning/Programming/Python/Practice/Interview questions/BOA/CE questions\|CE questions]] |
> > > > > 
> > > > 
> > > > > [!g-white]- practice problems
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | practice problems | [[Learning/Programming/Python/Practice/Interview questions/practice problems/Instance Methods, Class Methods, Static Methods and Alternative Constructors practice\|Instance Methods, Class Methods, Static Methods and Alternative Constructors practice]] |
> > > > > 
> > > 
> > > > [!g-white]- Practice questions
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Practice questions | [[Learning/Programming/Python/Practice/Practice questions/1. re, os.scandir, Path, sets, exceptions\|1. re, os.scandir, Path, sets, exceptions]] |
> > > > | Design Patterns | [[Learning/Programming/Python/Practice/Practice questions/Design Patterns/Abstract factory pattern\|Abstract factory pattern]] |
> > > > | My custom packages | [[Learning/Programming/Python/Practice/Practice questions/My custom packages/abstract class\|abstract class]] |
> > > > 
> > > > > [!g-white]- Design Patterns
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Design Patterns | [[Learning/Programming/Python/Practice/Practice questions/Design Patterns/Abstract factory pattern\|Abstract factory pattern]] |
> > > > > 
> > > > 
> > > > > [!g-white]- My custom packages
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | My custom packages | [[Learning/Programming/Python/Practice/Practice questions/My custom packages/abstract class\|abstract class]] |
> > > > > 
> > > 
> > > > [!g-white]- udemy
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | udemy | [[Learning/Programming/Python/Practice/udemy/Youtube links\|Youtube links]] |
> > > > | 210+ Exercises - Python Standard Libraries | [[Learning/Programming/Python/Practice/udemy/210+ Exercises - Python Standard Libraries/210+ Exercises - Python Standard Libraries\|210+ Exercises - Python Standard Libraries]] |
> > > > | 380+ Exercises - Python Programming Mega Pack - Built-in | [[Learning/Programming/Python/Practice/udemy/380+ Exercises - Python Programming Mega Pack - Built-in/380+ Exercises - Python Programming Mega Pack - Built-in\|380+ Exercises - Python Programming Mega Pack - Built-in]] |
> > > > | Master Python by Coding 100 Practical Problems | [[Learning/Programming/Python/Practice/udemy/Master Python by Coding 100 Practical Problems/Master Python by Coding 100 Practical Problems\|Master Python by Coding 100 Practical Problems]] |
> > > > | Modern Python Application Development in Practice! | [[Learning/Programming/Python/Practice/udemy/Modern Python Application Development in Practice!/Modern Python Application Development in Practice!\|Modern Python Application Development in Practice!]] |
> > > > | PCPP1 - Become Certified Professional in Python Programming 1 | [[Learning/Programming/Python/Practice/udemy/PCPP1 - Become Certified Professional in Python Programming 1/PCPP1 - Become Certified Professional in Python Programming 1\|PCPP1 - Become Certified Professional in Python Programming 1]] |
> > > > | Python 3 Standard Library Essentials | [[Learning/Programming/Python/Practice/udemy/Python 3 Standard Library Essentials/Python 3 Standard Library Essentials\|Python 3 Standard Library Essentials]] |
> > > > | Python Best Parts - Standard Library (Beginner to Advanced) | [[Learning/Programming/Python/Practice/udemy/Python Best Parts - Standard Library (Beginner to Advanced)/Python Best Parts - Standard Library (Beginner to Advanced)\|Python Best Parts - Standard Library (Beginner to Advanced)]] |
> > > > | Python Certification Exam PCAP-31-03 Practice Tests [2024] | [[Learning/Programming/Python/Practice/udemy/Python Certification Exam PCAP-31-03 Practice Tests [2024]/Python Certification Exam PCAP-31-03 Practice Tests [2024]\|Python Certification Exam PCAP-31-03 Practice Tests [2024]]] |
> > > > | Python Certification Exam PCEP-30-02 - Preparation (2025) | [[Learning/Programming/Python/Practice/udemy/Python Certification Exam PCEP-30-02 - Preparation (2025)/Python Certification Exam PCEP-30-02 - Preparation (2025)\|Python Certification Exam PCEP-30-02 - Preparation (2025)]] |
> > > > | Python Exercises for Beginners - Solve 100+ Coding Challenges | [[Learning/Programming/Python/Practice/udemy/Python Exercises for Beginners - Solve 100+ Coding Challenges/Python Exercises for Beginners - Solve 100+ Coding Challenges\|Python Exercises for Beginners - Solve 100+ Coding Challenges]] |
> > > > | Python Programming - 200+ Exercises for Practice | [[Learning/Programming/Python/Practice/udemy/Python Programming - 200+ Exercises for Practice/Python Programming - 200+ Exercises for Practice\|Python Programming - 200+ Exercises for Practice]] |
> > > > 
> > > > > [!g-white]- 210+ Exercises - Python Standard Libraries
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | 210+ Exercises - Python Standard Libraries | [[Learning/Programming/Python/Practice/udemy/210+ Exercises - Python Standard Libraries/210+ Exercises - Python Standard Libraries\|210+ Exercises - Python Standard Libraries]] |
> > > > > 
> > > > 
> > > > > [!g-white]- 380+ Exercises - Python Programming Mega Pack - Built-in
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | 380+ Exercises - Python Programming Mega Pack - Built-in | [[Learning/Programming/Python/Practice/udemy/380+ Exercises - Python Programming Mega Pack - Built-in/380+ Exercises - Python Programming Mega Pack - Built-in\|380+ Exercises - Python Programming Mega Pack - Built-in]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Master Python by Coding 100 Practical Problems
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Master Python by Coding 100 Practical Problems | [[Learning/Programming/Python/Practice/udemy/Master Python by Coding 100 Practical Problems/Master Python by Coding 100 Practical Problems\|Master Python by Coding 100 Practical Problems]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Modern Python Application Development in Practice!
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Modern Python Application Development in Practice! | [[Learning/Programming/Python/Practice/udemy/Modern Python Application Development in Practice!/Modern Python Application Development in Practice!\|Modern Python Application Development in Practice!]] |
> > > > > 
> > > > 
> > > > > [!g-white]- PCPP1 - Become Certified Professional in Python Programming 1
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | PCPP1 - Become Certified Professional in Python Programming 1 | [[Learning/Programming/Python/Practice/udemy/PCPP1 - Become Certified Professional in Python Programming 1/PCPP1 - Become Certified Professional in Python Programming 1\|PCPP1 - Become Certified Professional in Python Programming 1]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Python 3 Standard Library Essentials
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Python 3 Standard Library Essentials | [[Learning/Programming/Python/Practice/udemy/Python 3 Standard Library Essentials/Python 3 Standard Library Essentials\|Python 3 Standard Library Essentials]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Python Best Parts - Standard Library (Beginner to Advanced)
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Python Best Parts - Standard Library (Beginner to Advanced) | [[Learning/Programming/Python/Practice/udemy/Python Best Parts - Standard Library (Beginner to Advanced)/Python Best Parts - Standard Library (Beginner to Advanced)\|Python Best Parts - Standard Library (Beginner to Advanced)]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Python Certification Exam PCAP-31-03 Practice Tests [2024]
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Python Certification Exam PCAP-31-03 Practice Tests [2024] | [[Learning/Programming/Python/Practice/udemy/Python Certification Exam PCAP-31-03 Practice Tests [2024]/Python Certification Exam PCAP-31-03 Practice Tests [2024]\|Python Certification Exam PCAP-31-03 Practice Tests [2024]]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Python Certification Exam PCEP-30-02 - Preparation (2025)
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Python Certification Exam PCEP-30-02 - Preparation (2025) | [[Learning/Programming/Python/Practice/udemy/Python Certification Exam PCEP-30-02 - Preparation (2025)/Python Certification Exam PCEP-30-02 - Preparation (2025)\|Python Certification Exam PCEP-30-02 - Preparation (2025)]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Python Exercises for Beginners - Solve 100+ Coding Challenges
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Python Exercises for Beginners - Solve 100+ Coding Challenges | [[Learning/Programming/Python/Practice/udemy/Python Exercises for Beginners - Solve 100+ Coding Challenges/Python Exercises for Beginners - Solve 100+ Coding Challenges\|Python Exercises for Beginners - Solve 100+ Coding Challenges]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Python Programming - 200+ Exercises for Practice
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Python Programming - 200+ Exercises for Practice | [[Learning/Programming/Python/Practice/udemy/Python Programming - 200+ Exercises for Practice/Python Programming - 200+ Exercises for Practice\|Python Programming - 200+ Exercises for Practice]] |
> > > > > 
> > 
> > > [!g-white]- Problems and Solutions
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | Problems and Solutions | [[Learning/Programming/Python/Problems and Solutions/problem 1\|problem 1]] |
> > > 
> > 
> > > [!g-white]- pyspark
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | pyspark | [[Learning/Programming/Python/pyspark/questions\|questions]] |
> > > | udemy - PySpark - Apache Spark Programming for Beginners | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 1 - Understanding Big Data and Distributed Data Processing/1. What is Big Data and How it Started\|1. What is Big Data and How it Started]] |
> > > 
> > > > [!g-white]- udemy - PySpark - Apache Spark Programming for Beginners
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | udemy - PySpark - Apache Spark Programming for Beginners | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Summary\|Summary]] |
> > > > | Section 1 - Understanding Big Data and Distributed Data Processing | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 1 - Understanding Big Data and Distributed Data Processing/1. What is Big Data and How it Started\|1. What is Big Data and How it Started]] |
> > > > | Section 10 - Spark On Your Laptop IDE | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 10 - Spark On Your Laptop IDE/49. Setup your Laptop for Spark Development\|49. Setup your Laptop for Spark Development]] |
> > > > | Section 11 - Spark Execution Model - Old Videos | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 11 - Spark Execution Model - Old Videos/52. Execution Methods - How to Run Spark Programs\|52. Execution Methods - How to Run Spark Programs]] |
> > > > | Section 12 - Spark Programming Model and Developer Experience - Old Videos | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 12 - Spark Programming Model and Developer Experience - Old Videos/60. Creating Spark Project Build Configuration\|60. Creating Spark Project Build Configuration]] |
> > > > | Section 13 - Capstone Project | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 13 - Capstone Project/69. Project Source Code and Resources\|69. Project Source Code and Resources]] |
> > > > | Section 14 - Keep Learning | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 14 - Keep Learning/80. Final Word\|80. Final Word]] |
> > > > | Section 2 - Introduction to Apache Spark | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 2 - Introduction to Apache Spark/10. Download Resources\|10. Download Resources]] |
> > > > | Section 3 - Getting Started with Spark Programming | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 3 - Getting Started with Spark Programming/11. Starting Point - Data Engineering Spark and Spark Session\|11. Starting Point - Data Engineering Spark and Spark Session]] |
> > > > | Section 4 - Spark Data Types and Schema | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 4 - Spark Data Types and Schema/17. Spark Data Types\|17. Spark Data Types]] |
> > > > | Section 5 - Dataframe Transformations | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 5 - Dataframe Transformations/21. Adding Removing and Renaming Columns\|21. Adding Removing and Renaming Columns]] |
> > > > | Section 6 - Working with different data types | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 6 - Working with different data types/27. Working with Nulls\|27. Working with Nulls]] |
> > > > | Section 7 - Joins in Spark Dataframe | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 7 - Joins in Spark Dataframe/36. Introduction to Joins in Spark\|36. Introduction to Joins in Spark]] |
> > > > | Section 8 - Aggregations in Spark Dataframe | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 8 - Aggregations in Spark Dataframe/41. Simple Aggregation\|41. Simple Aggregation]] |
> > > > | Section 9 - UDF and Unit Testing | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 9 - UDF and Unit Testing/45. User-Defined Functions\|45. User-Defined Functions]] |
> > > > 
> > > > > [!g-white]- Section 1 - Understanding Big Data and Distributed Data Processing
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 1 - Understanding Big Data and Distributed Data Processing | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 1 - Understanding Big Data and Distributed Data Processing/1. What is Big Data and How it Started\|1. What is Big Data and How it Started]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 10 - Spark On Your Laptop IDE
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 10 - Spark On Your Laptop IDE | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 10 - Spark On Your Laptop IDE/49. Setup your Laptop for Spark Development\|49. Setup your Laptop for Spark Development]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 11 - Spark Execution Model - Old Videos
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 11 - Spark Execution Model - Old Videos | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 11 - Spark Execution Model - Old Videos/52. Execution Methods - How to Run Spark Programs\|52. Execution Methods - How to Run Spark Programs]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 12 - Spark Programming Model and Developer Experience - Old Videos
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 12 - Spark Programming Model and Developer Experience - Old Videos | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 12 - Spark Programming Model and Developer Experience - Old Videos/60. Creating Spark Project Build Configuration\|60. Creating Spark Project Build Configuration]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 13 - Capstone Project
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 13 - Capstone Project | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 13 - Capstone Project/69. Project Source Code and Resources\|69. Project Source Code and Resources]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 14 - Keep Learning
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 14 - Keep Learning | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 14 - Keep Learning/80. Final Word\|80. Final Word]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 2 - Introduction to Apache Spark
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 2 - Introduction to Apache Spark | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 2 - Introduction to Apache Spark/10. Download Resources\|10. Download Resources]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 3 - Getting Started with Spark Programming
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 3 - Getting Started with Spark Programming | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 3 - Getting Started with Spark Programming/11. Starting Point - Data Engineering Spark and Spark Session\|11. Starting Point - Data Engineering Spark and Spark Session]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 4 - Spark Data Types and Schema
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 4 - Spark Data Types and Schema | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 4 - Spark Data Types and Schema/17. Spark Data Types\|17. Spark Data Types]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 5 - Dataframe Transformations
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 5 - Dataframe Transformations | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 5 - Dataframe Transformations/21. Adding Removing and Renaming Columns\|21. Adding Removing and Renaming Columns]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 6 - Working with different data types
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 6 - Working with different data types | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 6 - Working with different data types/27. Working with Nulls\|27. Working with Nulls]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 7 - Joins in Spark Dataframe
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 7 - Joins in Spark Dataframe | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 7 - Joins in Spark Dataframe/36. Introduction to Joins in Spark\|36. Introduction to Joins in Spark]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 8 - Aggregations in Spark Dataframe
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 8 - Aggregations in Spark Dataframe | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 8 - Aggregations in Spark Dataframe/41. Simple Aggregation\|41. Simple Aggregation]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 9 - UDF and Unit Testing
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 9 - UDF and Unit Testing | [[Learning/Programming/Python/pyspark/udemy - PySpark - Apache Spark Programming for Beginners/Section 9 - UDF and Unit Testing/45. User-Defined Functions\|45. User-Defined Functions]] |
> > > > > 
> > 
> > > [!g-white]- Python Libraries and Methods
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | Python Libraries and Methods | [[Learning/Programming/Python/Python Libraries and Methods/String methods\|String methods]] |
> > > 
> > 
> > > [!g-white]- python MOC
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | python MOC | [[Learning/Programming/Python/python MOC/TODO\|TODO]] |
> > > | Advanced Python & Best Practices MOC | [[Learning/Programming/Python/python MOC/Advanced Python & Best Practices MOC/Advanced Python & Best Practices MOC\|Advanced Python & Best Practices MOC]] |
> > > | Control Flow & Functions MOC | [[Learning/Programming/Python/python MOC/Control Flow & Functions MOC/Conditionals and Booleans\|Conditionals and Booleans]] |
> > > | Data Types & Collections MOC | [[Learning/Programming/Python/python MOC/Data Types & Collections MOC/Data Types & Collections MOC\|Data Types & Collections MOC]] |
> > > | Dunder Methods & Special Functions MOC | [[Learning/Programming/Python/python MOC/Dunder Methods & Special Functions MOC/Dunder Methods & Special Functions MOC\|Dunder Methods & Special Functions MOC]] |
> > > | Exception Handling MOC | [[Learning/Programming/Python/python MOC/Exception Handling MOC/Exception Handling MOC\|Exception Handling MOC]] |
> > > | Extras Addendum MOC | [[Learning/Programming/Python/python MOC/Extras Addendum MOC/Extras Addendum MOC\|Extras Addendum MOC]] |
> > > | File Handling & Modules MOC | [[Learning/Programming/Python/python MOC/File Handling & Modules MOC/File Handling & Modules MOC\|File Handling & Modules MOC]] |
> > > | Important functions | [[Learning/Programming/Python/python MOC/Important functions/os functions\|os functions]] |
> > > | OOP MOC | [[Learning/Programming/Python/python MOC/OOP MOC/C3 Linerisation\|C3 Linerisation]] |
> > > | Operators & Expressions MOC | [[Learning/Programming/Python/python MOC/Operators & Expressions MOC/Operators & Expressions MOC\|Operators & Expressions MOC]] |
> > > | Packaging & Distribution MOC | [[Learning/Programming/Python/python MOC/Packaging & Distribution MOC/Packaging & Distribution MOC\|Packaging & Distribution MOC]] |
> > > | PyCharm | [[Learning/Programming/Python/python MOC/PyCharm/PyCharm tutorial\|PyCharm tutorial]] |
> > > | Python gotchas, epiphanies,errors,common pitfalls | [[Learning/Programming/Python/python MOC/Python gotchas, epiphanies,errors,common pitfalls/Mutable Default Arguments\|Mutable Default Arguments]] |
> > > | Python Standard Library & Utilities MOC | [[Learning/Programming/Python/python MOC/Python Standard Library & Utilities MOC/Advanced logging\|Advanced logging]] |
> > > 
> > > > [!g-white]- Advanced Python & Best Practices MOC
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Advanced Python & Best Practices MOC | [[Learning/Programming/Python/python MOC/Advanced Python & Best Practices MOC/Advanced Python & Best Practices MOC\|Advanced Python & Best Practices MOC]] |
> > > > 
> > > 
> > > > [!g-white]- Control Flow & Functions MOC
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Control Flow & Functions MOC | [[Learning/Programming/Python/python MOC/Control Flow & Functions MOC/Conditionals and Booleans\|Conditionals and Booleans]] |
> > > > 
> > > 
> > > > [!g-white]- Data Types & Collections MOC
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Data Types & Collections MOC | [[Learning/Programming/Python/python MOC/Data Types & Collections MOC/Data Types & Collections MOC\|Data Types & Collections MOC]] |
> > > > 
> > > 
> > > > [!g-white]- Dunder Methods & Special Functions MOC
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Dunder Methods & Special Functions MOC | [[Learning/Programming/Python/python MOC/Dunder Methods & Special Functions MOC/Dunder Methods & Special Functions MOC\|Dunder Methods & Special Functions MOC]] |
> > > > 
> > > 
> > > > [!g-white]- Exception Handling MOC
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Exception Handling MOC | [[Learning/Programming/Python/python MOC/Exception Handling MOC/Exception Handling MOC\|Exception Handling MOC]] |
> > > > 
> > > 
> > > > [!g-white]- Extras Addendum MOC
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Extras Addendum MOC | [[Learning/Programming/Python/python MOC/Extras Addendum MOC/Extras Addendum MOC\|Extras Addendum MOC]] |
> > > > 
> > > 
> > > > [!g-white]- File Handling & Modules MOC
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | File Handling & Modules MOC | [[Learning/Programming/Python/python MOC/File Handling & Modules MOC/File Handling & Modules MOC\|File Handling & Modules MOC]] |
> > > > | pathlib | [[Learning/Programming/Python/python MOC/File Handling & Modules MOC/pathlib/pathlib\|pathlib]] |
> > > > 
> > > > > [!g-white]- pathlib
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | pathlib | [[Learning/Programming/Python/python MOC/File Handling & Modules MOC/pathlib/pathlib\|pathlib]] |
> > > > > 
> > > 
> > > > [!g-white]- Important functions
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Important functions | [[Learning/Programming/Python/python MOC/Important functions/os functions\|os functions]] |
> > > > 
> > > 
> > > > [!g-white]- OOP MOC
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | OOP MOC | [[Learning/Programming/Python/python MOC/OOP MOC/C3 Linerisation\|C3 Linerisation]] |
> > > > 
> > > 
> > > > [!g-white]- Operators & Expressions MOC
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Operators & Expressions MOC | [[Learning/Programming/Python/python MOC/Operators & Expressions MOC/Operators & Expressions MOC\|Operators & Expressions MOC]] |
> > > > 
> > > 
> > > > [!g-white]- Packaging & Distribution MOC
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Packaging & Distribution MOC | [[Learning/Programming/Python/python MOC/Packaging & Distribution MOC/Packaging & Distribution MOC\|Packaging & Distribution MOC]] |
> > > > 
> > > 
> > > > [!g-white]- PyCharm
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | PyCharm | [[Learning/Programming/Python/python MOC/PyCharm/PyCharm tutorial\|PyCharm tutorial]] |
> > > > | plugins | [[Learning/Programming/Python/python MOC/PyCharm/plugins/ide_eval_reset\|ide_eval_reset]] |
> > > > 
> > > > > [!g-white]- plugins
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | plugins | [[Learning/Programming/Python/python MOC/PyCharm/plugins/ide_eval_reset\|ide_eval_reset]] |
> > > > > 
> > > 
> > > > [!g-white]- Python gotchas, epiphanies,errors,common pitfalls
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Python gotchas, epiphanies,errors,common pitfalls | [[Learning/Programming/Python/python MOC/Python gotchas, epiphanies,errors,common pitfalls/Mutable Default Arguments\|Mutable Default Arguments]] |
> > > > 
> > > 
> > > > [!g-white]- Python Standard Library & Utilities MOC
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Python Standard Library & Utilities MOC | [[Learning/Programming/Python/python MOC/Python Standard Library & Utilities MOC/Advanced logging\|Advanced logging]] |
> > > > | argparse | [[Learning/Programming/Python/python MOC/Python Standard Library & Utilities MOC/argparse/argparse\|argparse]] |
> > > > | BeautifulSoup module | [[Learning/Programming/Python/python MOC/Python Standard Library & Utilities MOC/BeautifulSoup module/BeautifulSoup module\|BeautifulSoup module]] |
> > > > | requests module | [[Learning/Programming/Python/python MOC/Python Standard Library & Utilities MOC/requests module/requests module\|requests module]] |
> > > > 
> > > > > [!g-white]- argparse
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | argparse | [[Learning/Programming/Python/python MOC/Python Standard Library & Utilities MOC/argparse/argparse\|argparse]] |
> > > > > 
> > > > 
> > > > > [!g-white]- BeautifulSoup module
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | BeautifulSoup module | [[Learning/Programming/Python/python MOC/Python Standard Library & Utilities MOC/BeautifulSoup module/BeautifulSoup module\|BeautifulSoup module]] |
> > > > > 
> > > > 
> > > > > [!g-white]- MoviePy
> > > > > 
> > > > > 
> > > > 
> > > > > [!g-white]- requests module
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | requests module | [[Learning/Programming/Python/python MOC/Python Standard Library & Utilities MOC/requests module/requests module\|requests module]] |
> > > > > 
> > > > 
> > > > > [!g-white]- selenium module
> > > > > 
> > > > > 
> > 
> > > [!g-white]- testing
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | testing | [[Learning/Programming/Python/testing/1. Introduction\|1. Introduction]] |
> > > | oreilly - mocking | [[Learning/Programming/Python/testing/oreilly - mocking/1. Introduction\|1. Introduction]] |
> > > | Udemy - Python Unit Testing Fundamentals | [[Learning/Programming/Python/testing/Udemy - Python Unit Testing Fundamentals/Section 1 - Unit Testing in Python/1. About This Course\|1. About This Course]] |
> > > 
> > > > [!g-white]- oreilly - mocking
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | oreilly - mocking | [[Learning/Programming/Python/testing/oreilly - mocking/1. Introduction\|1. Introduction]] |
> > > > 
> > > 
> > > > [!g-white]- Udemy - Python Unit Testing Fundamentals
> > > > 
> > > > 
> > > > > [!g-white]- Section 1 - Unit Testing in Python
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 1 - Unit Testing in Python | [[Learning/Programming/Python/testing/Udemy - Python Unit Testing Fundamentals/Section 1 - Unit Testing in Python/1. About This Course\|1. About This Course]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 10 - Reporting
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 10 - Reporting | [[Learning/Programming/Python/testing/Udemy - Python Unit Testing Fundamentals/Section 10 - Reporting/43. Module Overview\|43. Module Overview]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 11 - Course 2 - Conclusion - Unit Testing with Pytest
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 11 - Course 2 - Conclusion - Unit Testing with Pytest | [[Learning/Programming/Python/testing/Udemy - Python Unit Testing Fundamentals/Section 11 - Course 2 - Conclusion - Unit Testing with Pytest/46. Congrats\|46. Congrats]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 12 - Conclusion and Bonus
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 12 - Conclusion and Bonus | [[Learning/Programming/Python/testing/Udemy - Python Unit Testing Fundamentals/Section 12 - Conclusion and Bonus/47. Bonus\|47. Bonus]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 2 - Course 1  Start  - Python Unit Testing with unittest
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 2 - Course 1  Start  - Python Unit Testing with unittest | [[Learning/Programming/Python/testing/Udemy - Python Unit Testing Fundamentals/Section 2 - Course 1  Start  - Python Unit Testing with unittest/2. Course Resources\|2. Course Resources]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 3 - Unit Testing Fundamentals
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 3 - Unit Testing Fundamentals | [[Learning/Programming/Python/testing/Udemy - Python Unit Testing Fundamentals/Section 3 - Unit Testing Fundamentals/10. Unit Tests for a class\|10. Unit Tests for a class]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 4 - Best Practices
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 4 - Best Practices | [[Learning/Programming/Python/testing/Udemy - Python Unit Testing Fundamentals/Section 4 - Best Practices/19. Best Practices - Part 1 - Discussion\|19. Best Practices - Part 1 - Discussion]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 5 - Quiz
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 5 - Quiz | [[Learning/Programming/Python/testing/Udemy - Python Unit Testing Fundamentals/Section 5 - Quiz/Quiz 1 - Quiz\|Quiz 1 - Quiz]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 6 - Course 1 - Conclusion - Unit Testing with unittest module
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 6 - Course 1 - Conclusion - Unit Testing with unittest module | [[Learning/Programming/Python/testing/Udemy - Python Unit Testing Fundamentals/Section 6 - Course 1 - Conclusion - Unit Testing with unittest module/21. Congrats\|21. Congrats]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 7 - Course 2  Start  - Python Unit Testing with pytest
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 7 - Course 2  Start  - Python Unit Testing with pytest | [[Learning/Programming/Python/testing/Udemy - Python Unit Testing Fundamentals/Section 7 - Course 2  Start  - Python Unit Testing with pytest/22. Course Resources\|22. Course Resources]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 8 - Unit Testing with pytest
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 8 - Unit Testing with pytest | [[Learning/Programming/Python/testing/Udemy - Python Unit Testing Fundamentals/Section 8 - Unit Testing with pytest/24. Module Overview\|24. Module Overview]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 9 - Running Tests
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 9 - Running Tests | [[Learning/Programming/Python/testing/Udemy - Python Unit Testing Fundamentals/Section 9 - Running Tests/36. Module Overview\|36. Module Overview]] |
> > > > >
<!-- Python_END -->





# 🎬Media

```button
name Generate Markers and Folder Structure for <span style="font-size: 1.2em; font-weight: bold; color: #3b82f6;">media</span>
type chain
templater true
actions [
  {
    "type": "append text",
    "action": "<%* try { const currentFile = app.workspace.getActiveFile(); if (!currentFile || currentFile.path !== 'Tools/Obsidian/Plugins/Dataview/Untitled 1.md') { return; } const basePath = 'Media'; const folders = app.vault.getAllLoadedFiles().filter(file => file.children && file.path.startsWith(basePath + '/')).map(folder => folder.path.replace(basePath + '/', '').split('/')[0]).filter((value, index, self) => value && self.indexOf(value) === index); if (!folders.length) { tR += `Error: No subfolders found under ${basePath}`; return; } const content = await app.vault.read(currentFile); const sorted = Array.from(folders).sort(); const markerRegex = new RegExp(`^<!--\\\\s*${sorted[0]}_START\\\\s*-->`, 'm'); if (content.match(markerRegex)) { return; } const comments = sorted.map(folder => `<!-- ${folder}_START -->\\n<!-- ${folder}_END -->`).join('\\n\\n'); tR += comments; } catch (error) { tR += `Error: ${error.message}`; } %>"
  },
  {
    "type": "command",
    "action": "<%* try { const currentNote = 'Tools/Obsidian/Plugins/Dataview/Untitled 1.md'; const basePath = 'Media'; const folders = app.vault.getAllLoadedFiles().filter(file => file.children && file.path.startsWith(basePath + '/')).map(folder => ({ path: folder.path, title: folder.path.split('/').pop() })).filter((folder, index, self) => self.findIndex(f => f.path === folder.path) === index && folder.path.split('/').length === basePath.split('/').length + 1); if (!folders.length) { tR += `Error: No subfolders found under ${basePath}`; return; } for (const folder of folders) { const lastFolder = folder.path.split('/').pop(); const startMarker = `<!-- ${lastFolder}_START -->`; const endMarker = `<!-- ${lastFolder}_END -->`; const output = await tp.user.generateFolderStructure(folder.path, '> ', 3); console.log(`Checking ${startMarker} to ${endMarker} in ${currentNote}`); await tp.user.replaceInNote(currentNote, startMarker, endMarker, output); } } catch (error) { tR += `Error: ${error.message}`; } %>"
  }
]
```
<!-- BookVideos_START -->
> [!g-gray] BookVideos
> 
> > [!multi-column]
> > 
> > 
> > 
> > | Folder | First File Link |
> > | --- | --- |
> > |  | [[Media/BookVideos/Statistics\|Statistics]] |
> > 
> > > [!g-white]- Just Important videos
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | Just Important videos | [[Media/BookVideos/Just Important videos/Just Important videos\|Just Important videos]] |
> > > 
> > 
> > > [!g-white]- Python
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | Python | [[Media/BookVideos/Python/Python\|Python]] |
> > > | A Pythonic Adventure | [[Media/BookVideos/Python/A Pythonic Adventure/A Pythonic Adventure\|A Pythonic Adventure]] |
> > > | Fast Python | [[Media/BookVideos/Python/Fast Python/Fast Python\|Fast Python]] |
> > > | Learn AI-Assisted Python Programming | [[Media/BookVideos/Python/Learn AI-Assisted Python Programming/Learn AI-Assisted Python Programming\|Learn AI-Assisted Python Programming]] |
> > > | Practices of the Python Pro | [[Media/BookVideos/Python/Practices of the Python Pro/Practices of the Python Pro\|Practices of the Python Pro]] |
> > > | Publishing Python Packages | [[Media/BookVideos/Python/Publishing Python Packages/Publishing Python Packages\|Publishing Python Packages]] |
> > > | Python Concurrency with asyncio | [[Media/BookVideos/Python/Python Concurrency with asyncio/Python Concurrency with asyncio\|Python Concurrency with asyncio]] |
> > > | Python Database Course - SQLite, PostgreSQL, MySQL,SQLAlchemy | [[Media/BookVideos/Python/Python Database Course - SQLite, PostgreSQL, MySQL,SQLAlchemy/Python Database Course - SQLite, PostgreSQL, MySQL,SQLAlchemy\|Python Database Course - SQLite, PostgreSQL, MySQL,SQLAlchemy]] |
> > > | Python How-To | [[Media/BookVideos/Python/Python How-To/Python How-To\|Python How-To]] |
> > > | PythonRulebook | [[Media/BookVideos/Python/PythonRulebook/01_SyntaxStyle/comments_docstrings\|comments_docstrings]] |
> > > | The Python Apprentice, Journeyman, Master | [[Media/BookVideos/Python/The Python Apprentice, Journeyman, Master/The Python Apprentice, Journeyman, Master\|The Python Apprentice, Journeyman, Master]] |
> > > 
> > > > [!g-white]- A Pythonic Adventure
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | A Pythonic Adventure | [[Media/BookVideos/Python/A Pythonic Adventure/A Pythonic Adventure\|A Pythonic Adventure]] |
> > > > 
> > > 
> > > > [!g-white]- Fast Python
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Fast Python | [[Media/BookVideos/Python/Fast Python/Fast Python\|Fast Python]] |
> > > > 
> > > 
> > > > [!g-white]- Learn AI-Assisted Python Programming
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Learn AI-Assisted Python Programming | [[Media/BookVideos/Python/Learn AI-Assisted Python Programming/Learn AI-Assisted Python Programming\|Learn AI-Assisted Python Programming]] |
> > > > 
> > > 
> > > > [!g-white]- Practices of the Python Pro
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Practices of the Python Pro | [[Media/BookVideos/Python/Practices of the Python Pro/Practices of the Python Pro\|Practices of the Python Pro]] |
> > > > 
> > > 
> > > > [!g-white]- Publishing Python Packages
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Publishing Python Packages | [[Media/BookVideos/Python/Publishing Python Packages/Publishing Python Packages\|Publishing Python Packages]] |
> > > > 
> > > 
> > > > [!g-white]- Python Concurrency with asyncio
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Python Concurrency with asyncio | [[Media/BookVideos/Python/Python Concurrency with asyncio/Python Concurrency with asyncio\|Python Concurrency with asyncio]] |
> > > > 
> > > 
> > > > [!g-white]- Python Database Course - SQLite, PostgreSQL, MySQL,SQLAlchemy
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Python Database Course - SQLite, PostgreSQL, MySQL,SQLAlchemy | [[Media/BookVideos/Python/Python Database Course - SQLite, PostgreSQL, MySQL,SQLAlchemy/Python Database Course - SQLite, PostgreSQL, MySQL,SQLAlchemy\|Python Database Course - SQLite, PostgreSQL, MySQL,SQLAlchemy]] |
> > > > | Section 1 - Introduction | [[Media/BookVideos/Python/Python Database Course - SQLite, PostgreSQL, MySQL,SQLAlchemy/Section 1 - Introduction/1. Getting the Most Out of This Course\|1. Getting the Most Out of This Course]] |
> > > > | Section 10 - MySQL In Python | [[Media/BookVideos/Python/Python Database Course - SQLite, PostgreSQL, MySQL,SQLAlchemy/Section 10 - MySQL In Python/80. What is MySQL?.md\|80. What is MySQL?]] |
> > > > | Section 11 - Employee Management System -MySQL App | [[Media/BookVideos/Python/Python Database Course - SQLite, PostgreSQL, MySQL,SQLAlchemy/Section 11 - Employee Management System -MySQL App/92. What you will make by the end of the section\|92. What you will make by the end of the section]] |
> > > > | Section 12 - PostgreSQL In Python | [[Media/BookVideos/Python/Python Database Course - SQLite, PostgreSQL, MySQL,SQLAlchemy/Section 12 - PostgreSQL In Python/100. Insert and Select Data using SQL Statements\|100. Insert and Select Data using SQL Statements]] |
> > > > | Section 13 - HCM using PostgreSQL | [[Media/BookVideos/Python/Python Database Course - SQLite, PostgreSQL, MySQL,SQLAlchemy/Section 13 - HCM using PostgreSQL/104. What you will make by the end of the section\|104. What you will make by the end of the section]] |
> > > > | Section 14 - SQL Server (MS SQL) using Python | [[Media/BookVideos/Python/Python Database Course - SQLite, PostgreSQL, MySQL,SQLAlchemy/Section 14 - SQL Server (MS SQL) using Python/106. Connect SQL Server using pyodbc Library\|106. Connect SQL Server using pyodbc Library]] |
> > > > | Section 15 - Bonus Lecture | [[Media/BookVideos/Python/Python Database Course - SQLite, PostgreSQL, MySQL,SQLAlchemy/Section 15 - Bonus Lecture/109. Bonus Lecture\|109. Bonus Lecture]] |
> > > > | Section 2 - A Comprehensive Python Starter Kit | [[Media/BookVideos/Python/Python Database Course - SQLite, PostgreSQL, MySQL,SQLAlchemy/Section 2 - A Comprehensive Python Starter Kit/10. Boolean Expressions\|10. Boolean Expressions]] |
> > > > | Section 3 - Introduction to Databases in Python | [[Media/BookVideos/Python/Python Database Course - SQLite, PostgreSQL, MySQL,SQLAlchemy/Section 3 - Introduction to Databases in Python/39. What is a Database?.md\|39. What is a Database?]] |
> > > > | Section 4 - SQLite In Python | [[Media/BookVideos/Python/Python Database Course - SQLite, PostgreSQL, MySQL,SQLAlchemy/Section 4 - SQLite In Python/43. What is SQL?.md\|43. What is SQL?]] |
> > > > | Section 5 - Real Project - Password Manager using SQLite | [[Media/BookVideos/Python/Python Database Course - SQLite, PostgreSQL, MySQL,SQLAlchemy/Section 5 - Real Project - Password Manager using SQLite/56. What you will make by the end of the section\|56. What you will make by the end of the section]] |
> > > > | Section 6 - SQL Alchemy Core | [[Media/BookVideos/Python/Python Database Course - SQLite, PostgreSQL, MySQL,SQLAlchemy/Section 6 - SQL Alchemy Core/61. What is SQLAlchemy?.md\|61. What is SQLAlchemy?]] |
> > > > | Section 7 - Password Manager Project using SQLAlchemy Core | [[Media/BookVideos/Python/Python Database Course - SQLite, PostgreSQL, MySQL,SQLAlchemy/Section 7 - Password Manager Project using SQLAlchemy Core/68. What you will make by the end of the section\|68. What you will make by the end of the section]] |
> > > > | Section 8 - SQL Alchemy ORM | [[Media/BookVideos/Python/Python Database Course - SQLite, PostgreSQL, MySQL,SQLAlchemy/Section 8 - SQL Alchemy ORM/70. Connecting Database and Create Table using SQLAlchemy ORM\|70. Connecting Database and Create Table using SQLAlchemy ORM]] |
> > > > | Section 9 - Password Manager using SQLAlchemy ORM | [[Media/BookVideos/Python/Python Database Course - SQLite, PostgreSQL, MySQL,SQLAlchemy/Section 9 - Password Manager using SQLAlchemy ORM/78. What you will make by the end of the section\|78. What you will make by the end of the section]] |
> > > > 
> > > > > [!g-white]- Section 1 - Introduction
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 1 - Introduction | [[Media/BookVideos/Python/Python Database Course - SQLite, PostgreSQL, MySQL,SQLAlchemy/Section 1 - Introduction/1. Getting the Most Out of This Course\|1. Getting the Most Out of This Course]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 10 - MySQL In Python
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 10 - MySQL In Python | [[Media/BookVideos/Python/Python Database Course - SQLite, PostgreSQL, MySQL,SQLAlchemy/Section 10 - MySQL In Python/80. What is MySQL?.md\|80. What is MySQL?]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 11 - Employee Management System -MySQL App
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 11 - Employee Management System -MySQL App | [[Media/BookVideos/Python/Python Database Course - SQLite, PostgreSQL, MySQL,SQLAlchemy/Section 11 - Employee Management System -MySQL App/92. What you will make by the end of the section\|92. What you will make by the end of the section]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 12 - PostgreSQL In Python
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 12 - PostgreSQL In Python | [[Media/BookVideos/Python/Python Database Course - SQLite, PostgreSQL, MySQL,SQLAlchemy/Section 12 - PostgreSQL In Python/100. Insert and Select Data using SQL Statements\|100. Insert and Select Data using SQL Statements]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 13 - HCM using PostgreSQL
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 13 - HCM using PostgreSQL | [[Media/BookVideos/Python/Python Database Course - SQLite, PostgreSQL, MySQL,SQLAlchemy/Section 13 - HCM using PostgreSQL/104. What you will make by the end of the section\|104. What you will make by the end of the section]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 14 - SQL Server (MS SQL) using Python
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 14 - SQL Server (MS SQL) using Python | [[Media/BookVideos/Python/Python Database Course - SQLite, PostgreSQL, MySQL,SQLAlchemy/Section 14 - SQL Server (MS SQL) using Python/106. Connect SQL Server using pyodbc Library\|106. Connect SQL Server using pyodbc Library]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 15 - Bonus Lecture
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 15 - Bonus Lecture | [[Media/BookVideos/Python/Python Database Course - SQLite, PostgreSQL, MySQL,SQLAlchemy/Section 15 - Bonus Lecture/109. Bonus Lecture\|109. Bonus Lecture]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 2 - A Comprehensive Python Starter Kit
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 2 - A Comprehensive Python Starter Kit | [[Media/BookVideos/Python/Python Database Course - SQLite, PostgreSQL, MySQL,SQLAlchemy/Section 2 - A Comprehensive Python Starter Kit/10. Boolean Expressions\|10. Boolean Expressions]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 3 - Introduction to Databases in Python
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 3 - Introduction to Databases in Python | [[Media/BookVideos/Python/Python Database Course - SQLite, PostgreSQL, MySQL,SQLAlchemy/Section 3 - Introduction to Databases in Python/39. What is a Database?.md\|39. What is a Database?]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 4 - SQLite In Python
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 4 - SQLite In Python | [[Media/BookVideos/Python/Python Database Course - SQLite, PostgreSQL, MySQL,SQLAlchemy/Section 4 - SQLite In Python/43. What is SQL?.md\|43. What is SQL?]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 5 - Real Project - Password Manager using SQLite
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 5 - Real Project - Password Manager using SQLite | [[Media/BookVideos/Python/Python Database Course - SQLite, PostgreSQL, MySQL,SQLAlchemy/Section 5 - Real Project - Password Manager using SQLite/56. What you will make by the end of the section\|56. What you will make by the end of the section]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 6 - SQL Alchemy Core
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 6 - SQL Alchemy Core | [[Media/BookVideos/Python/Python Database Course - SQLite, PostgreSQL, MySQL,SQLAlchemy/Section 6 - SQL Alchemy Core/61. What is SQLAlchemy?.md\|61. What is SQLAlchemy?]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 7 - Password Manager Project using SQLAlchemy Core
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 7 - Password Manager Project using SQLAlchemy Core | [[Media/BookVideos/Python/Python Database Course - SQLite, PostgreSQL, MySQL,SQLAlchemy/Section 7 - Password Manager Project using SQLAlchemy Core/68. What you will make by the end of the section\|68. What you will make by the end of the section]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 8 - SQL Alchemy ORM
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 8 - SQL Alchemy ORM | [[Media/BookVideos/Python/Python Database Course - SQLite, PostgreSQL, MySQL,SQLAlchemy/Section 8 - SQL Alchemy ORM/70. Connecting Database and Create Table using SQLAlchemy ORM\|70. Connecting Database and Create Table using SQLAlchemy ORM]] |
> > > > > 
> > > > 
> > > > > [!g-white]- Section 9 - Password Manager using SQLAlchemy ORM
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | Section 9 - Password Manager using SQLAlchemy ORM | [[Media/BookVideos/Python/Python Database Course - SQLite, PostgreSQL, MySQL,SQLAlchemy/Section 9 - Password Manager using SQLAlchemy ORM/78. What you will make by the end of the section\|78. What you will make by the end of the section]] |
> > > > > 
> > > 
> > > > [!g-white]- Python How-To
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | Python How-To | [[Media/BookVideos/Python/Python How-To/Python How-To\|Python How-To]] |
> > > > 
> > > 
> > > > [!g-white]- PythonRulebook
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | PythonRulebook | [[Media/BookVideos/Python/PythonRulebook/PythonRulebook\|PythonRulebook]] |
> > > > | 01_SyntaxStyle | [[Media/BookVideos/Python/PythonRulebook/01_SyntaxStyle/comments_docstrings\|comments_docstrings]] |
> > > > | 02_ControlFlow | [[Media/BookVideos/Python/PythonRulebook/02_ControlFlow/exceptions_handling\|exceptions_handling]] |
> > > > | 03_Functions | [[Media/BookVideos/Python/PythonRulebook/03_Functions/args_kwargs\|args_kwargs]] |
> > > > | 04_OOP | [[Media/BookVideos/Python/PythonRulebook/04_OOP/classes_vs_dataclasses\|classes_vs_dataclasses]] |
> > > > | 05_Collections | [[Media/BookVideos/Python/PythonRulebook/05_Collections/collections_module\|collections_module]] |
> > > > | 06_ModulesPackages | [[Media/BookVideos/Python/PythonRulebook/06_ModulesPackages/__init__\|__init__]] |
> > > > | 07_FileIO | [[Media/BookVideos/Python/PythonRulebook/07_FileIO/encoding_utf8\|encoding_utf8]] |
> > > > | 08_Concurrency | [[Media/BookVideos/Python/PythonRulebook/08_Concurrency/asyncio_bestpractices\|asyncio_bestpractices]] |
> > > > | 09_Performance | [[Media/BookVideos/Python/PythonRulebook/09_Performance/bigO_pythonic\|bigO_pythonic]] |
> > > > | 10_TestsDebugging | [[Media/BookVideos/Python/PythonRulebook/10_TestsDebugging/asserts_vs_exceptions\|asserts_vs_exceptions]] |
> > > > | 11_Security | [[Media/BookVideos/Python/PythonRulebook/11_Security/dependency_security\|dependency_security]] |
> > > > | 12_ModernPython | [[Media/BookVideos/Python/PythonRulebook/12_ModernPython/dataclasses\|dataclasses]] |
> > > > | 13_BonusChapters | [[Media/BookVideos/Python/PythonRulebook/13_BonusChapters/code_reviews\|code_reviews]] |
> > > > 
> > > > > [!g-white]- 01_SyntaxStyle
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | 01_SyntaxStyle | [[Media/BookVideos/Python/PythonRulebook/01_SyntaxStyle/comments_docstrings\|comments_docstrings]] |
> > > > > 
> > > > 
> > > > > [!g-white]- 02_ControlFlow
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | 02_ControlFlow | [[Media/BookVideos/Python/PythonRulebook/02_ControlFlow/exceptions_handling\|exceptions_handling]] |
> > > > > 
> > > > 
> > > > > [!g-white]- 03_Functions
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | 03_Functions | [[Media/BookVideos/Python/PythonRulebook/03_Functions/args_kwargs\|args_kwargs]] |
> > > > > 
> > > > 
> > > > > [!g-white]- 04_OOP
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | 04_OOP | [[Media/BookVideos/Python/PythonRulebook/04_OOP/classes_vs_dataclasses\|classes_vs_dataclasses]] |
> > > > > 
> > > > 
> > > > > [!g-white]- 05_Collections
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | 05_Collections | [[Media/BookVideos/Python/PythonRulebook/05_Collections/collections_module\|collections_module]] |
> > > > > 
> > > > 
> > > > > [!g-white]- 06_ModulesPackages
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | 06_ModulesPackages | [[Media/BookVideos/Python/PythonRulebook/06_ModulesPackages/__init__\|__init__]] |
> > > > > 
> > > > 
> > > > > [!g-white]- 07_FileIO
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | 07_FileIO | [[Media/BookVideos/Python/PythonRulebook/07_FileIO/encoding_utf8\|encoding_utf8]] |
> > > > > 
> > > > 
> > > > > [!g-white]- 08_Concurrency
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | 08_Concurrency | [[Media/BookVideos/Python/PythonRulebook/08_Concurrency/asyncio_bestpractices\|asyncio_bestpractices]] |
> > > > > 
> > > > 
> > > > > [!g-white]- 09_Performance
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | 09_Performance | [[Media/BookVideos/Python/PythonRulebook/09_Performance/bigO_pythonic\|bigO_pythonic]] |
> > > > > 
> > > > 
> > > > > [!g-white]- 10_TestsDebugging
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | 10_TestsDebugging | [[Media/BookVideos/Python/PythonRulebook/10_TestsDebugging/asserts_vs_exceptions\|asserts_vs_exceptions]] |
> > > > > 
> > > > 
> > > > > [!g-white]- 11_Security
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | 11_Security | [[Media/BookVideos/Python/PythonRulebook/11_Security/dependency_security\|dependency_security]] |
> > > > > 
> > > > 
> > > > > [!g-white]- 12_ModernPython
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | 12_ModernPython | [[Media/BookVideos/Python/PythonRulebook/12_ModernPython/dataclasses\|dataclasses]] |
> > > > > 
> > > > 
> > > > > [!g-white]- 13_BonusChapters
> > > > > 
> > > > > | Folder | First File Link |
> > > > > | --- | --- |
> > > > > | 13_BonusChapters | [[Media/BookVideos/Python/PythonRulebook/13_BonusChapters/code_reviews\|code_reviews]] |
> > > > > 
> > > 
> > > > [!g-white]- The Python Apprentice, Journeyman, Master
> > > > 
> > > > | Folder | First File Link |
> > > > | --- | --- |
> > > > | The Python Apprentice, Journeyman, Master | [[Media/BookVideos/Python/The Python Apprentice, Journeyman, Master/The Python Apprentice, Journeyman, Master\|The Python Apprentice, Journeyman, Master]] |
> > > > 
> > > > > [!g-white]- 2.Pluralsight.Python.Beyond.The.Basics
> > > > > 
> > > > > 
> > > > 
> > > > > [!g-white]- 3.Advanced Python
> > > > > 
> > > > >
<!-- BookVideos_END -->

<!-- Entertainment_START -->
> [!g-gray] Entertainment
> 
> > [!multi-column]
> > 
> > 
> > No files
> > 
> > > [!g-white]- Songs
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | Songs | [[Media/Entertainment/Songs/Links\|Links]] |
> > >
<!-- Entertainment_END -->

<!-- books_START -->
> [!g-gray] books
> 
> > [!multi-column]
> > 
> > 
> > 
> > | Folder | First File Link |
> > | --- | --- |
> > |  | [[Media/books/A First Course in Probability - Sheldon Ross\|A First Course in Probability - Sheldon Ross]] |
> > 
> > > [!g-white]- kindle highlights
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | kindle highlights | [[Media/books/kindle highlights/Balagurusamy-Object Oriented Programming With C++\|Balagurusamy-Object Oriented Programming With C++]] |
> > > 
> > 
> > > [!g-white]- Make It Stick_ The Science of Successful L - Peter C. Brown
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | Make It Stick_ The Science of Successful L - Peter C. Brown | [[Media/books/Make It Stick_ The Science of Successful L - Peter C. Brown/01-index_split_000\|01-index_split_000]] |
> > > 
> > 
> > > [!g-white]- test
> > > 
> > > | Folder | First File Link |
> > > | --- | --- |
> > > | test | [[Media/books/test/11 Finding boundaries with style\|11 Finding boundaries with style]] |
> > >
<!-- books_END -->

<!-- youtube video topics 1_START -->
> [!g-gray] youtube video topics 1
> 
> > [!multi-column]
> > 
> > 
> > 
> > | Folder | First File Link |
> > | --- | --- |
> > |  | [[Media/youtube video topics 1/funny\|funny]] |
> >
<!-- youtube video topics 1_END -->

# 🧠**Brain & Cognitive Sciences**
- **How to Study**
    - Neuroscience of Learning and Memory
        - Must Read Books
- NLP course by study glows

- [[.Long-Term Data Storage Options\|.Long-Term Data Storage Options]]
- **Obsidian**
    - Color theory
    - Youtube - Mastering Obsidian
	    - [[Digital Tools/Obsidian/Youtube - Mastering Obsidian/VideoNotes - Youtube - Mastering Obsidian\|Digital Tools/Obsidian/Youtube - Mastering Obsidian/VideoNotes - Youtube - Mastering Obsidian]]

# **Media & Entertainment**
- Youtube video topics



# 🧘🧿 **Personal Growth & Development**
- MOT
- **Digital Tools**
```dataview 
TABLE join(rows.file.link, " | ") as Files
FROM "Digital Tools"
GROUP BY file.folder as Folder
```

# **Extra Categories for Future Proofing:**

- **Travel & Adventures**
    
    - [Your travel logs, planning, and experiences]
- 💰**Finance & Budgeting**
    
    - [Your monthly budget, savings, investments]
- **Hobbies & Interests**
    
    - [Specific hobbies like painting, music, sports, etc.]
- **Social & Networking**
    
    - [Events, meetups, connections, and networking notes]
- 🥼**Research & Projects**
    
    - [Specific research topics or personal projects you're working on]
    - 
# [Vault Info](https://github.com/TfTHacker/DashboardPlusPlus/blob/master/Dashboard%2B%2B.md#vault-info)

- 🗄️ Recent file updates `$=dv.list(dv.pages('').sort(f=>f.file.mtime.ts,"desc").limit(10).file.link)`
- 🔖 Tagged: favorite `$=dv.list(dv.pages('#favorite').sort(f=>f.file.name,"desc").limit(4).file.link)`
- 〽️ Stats
    - File Count: `$=dv.pages().length`
    - Personal recipes: `$=dv.pages('"Family/Recipes"').length`






