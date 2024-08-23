# Quiz
 <!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Recipe Fetch</title>
    <link rel="stylesheet" href="style.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
</head>

<body>
    <header>
        <nav>
            <h1>Recipe App</h1>
            <form>
                <input type="text" placeholder="Search for recipe" class="search-box">
                <button type="submit" class="search-btn">Search</button>
            </form>
        </nav>
    </header>
    <main>
        <section>
            <div class="recipe-container">
                <h2>Search your favourite recipe</h2>
            </div>
            <div class="recipe-detail">
                <button type="button" class="recipe-close-btn">
                    <i class="fas fa-times"></i>
                </button>
                <div class="recipe-detail-content"></div>
            </div>
        </section>
    </main>
    <script src="index.js"></script>
</body>

</html>
