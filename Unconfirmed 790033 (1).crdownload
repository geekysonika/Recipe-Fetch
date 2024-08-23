const searchBox = document.querySelector('.search-box');
const searchButton = document.querySelector('.search-btn');
const recipeContainer = document.querySelector('.recipe-container');
const recipeDetailContent = document.querySelector('.recipe-detail-content');
const closeBtn = document.querySelector('.recipe-close-btn');

const fetchRecipe = async (query) => {
    recipeContainer.innerHTML = "<h2>Fetching recipes...</h2>";
    try {
        const data = await fetch(`https://www.themealdb.com/api/json/v1/1/search.php?s=${query}`);
        const response = await data.json();
        recipeContainer.innerHTML = "";
        response.meals.forEach(meal => {
            const recipeDiv = document.createElement('div');
            recipeDiv.classList.add('recipe');
            recipeDiv.innerHTML = `
            <img src="${meal.strMealThumb}">
            <h3>${meal.strMeal}</h3>
            <p><span>${meal.strArea}</span> Dish</p>
            <p>Belongs to <span>${meal.strCategory}</span> category</p>
         `
            const button = document.createElement('button');
            button.textContent = "View Recipe";
            recipeDiv.appendChild(button);
            button.addEventListener('click', () => {

                openRecipePopUp(meal);
            });
            recipeContainer.appendChild(recipeDiv);
        });
    } catch (error) {
        recipeContainer.innerHTML = "<h2>Error in fetching recipe..</h2>";
    }
}

//function to fetch ingedients
const fetchIngredients = (meal) => {
    let IngredientList = "";
    for (let i = 1; i <= 20; i++) {
        const ingredient = meal[`strIngredient${i}`];

        if (ingredient) {
            const measure = meal[`strMeasure${i}`];
            IngredientList += `<li>${measure}${ingredient}</li>`
        }
        else {
            break;
        }
    }
    return IngredientList;
}

const openRecipePopUp = (meal) => {
    recipeDetailContent.innerHTML = `
    <h2 class="recipeName">${meal.strMeal}</h2>
    <h3>Ingredients:</h3>
    <ul class="ingredientList">${fetchIngredients(meal)}</ul?
    <div class="recipeInstructions">
    <h3>Instructions:</h3>
    <p>${meal.strInstructions}</p>
    </div>
    `;
    recipeDetailContent.parentElement.style.display = "block";
}
closeBtn.addEventListener('click', () => {
    recipeDetailContent.parentElement.style.display = "none";
})
searchButton.addEventListener('click', (e) => {
    e.preventDefault();
    const searchInput = searchBox.value.trim();
    if (!searchInput) {
        recipeContainer.innerHTML = `<h2>type the meal in the search box.</h2>`;
        return;
    }
    fetchRecipe(searchInput);
    console.log("button clicked");
})