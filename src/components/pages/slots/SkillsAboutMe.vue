<template>
    <p>You'll usually find me working with the following tech:</p>
    <div class="frontend">
        <div class="skills-card-header">
            <i class="fa-sharp fa-solid fa-display fa-2x"></i>
            <h4 class="fe">Front-End</h4>
        </div>
        <ul class="no-list-style">
            <li>HTML & CSS</li>
            <li>Bootstrap / Tailwind CSS</li>
            <li>Vue.js</li><br>
        </ul>
    </div>
    <div class="backend">
        <div class="skills-card-header">
            <i class="fa-sharp fa-solid fa-database fa-2x"></i>
            <h4>Back-End</h4>
        </div>
        <ul class="no-list-style">
            <li>PHP 7.4</li>
            <li>Laravel 9</li>
            <li>Databases (MySQL & MongoDB)</li>
            <li>Slim 4 (REST API Development)</li>
        </ul>
    </div>
    <div class="tools">
        <div>
            <div class="skills-card-header">
                <i class="fa-solid fa-screwdriver-wrench fa-2x"></i>
                <h4>Tooling</h4>
            </div>
            <ul class="no-list-style">
                <li>Version Control (Git)</li>
                <li>Cypress</li>
                <li>Unit Testing (PHPUnit & Vitest)</li>
                <li>Static Analysis (PHPStan)</li>
            </ul>
        </div>
    </div>
</template>

<style scoped>
h4 {
    margin-left: 0.5rem;
}

li {
    margin-bottom: 0.4rem;
}

.no-list-style {
    list-style-type: none;
    padding-left: 1rem;
}

.skills-card-header {
    display: flex;
    justify-content: center;
    align-items: center;
}
</style>