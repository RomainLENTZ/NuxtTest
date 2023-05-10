<template>
    <main>
        <h1>Homepage</h1>
        <nav>
            <ul>
                <li><nuxt-link to="/about">About</nuxt-link></li>
                <li><nuxt-link to="/contact">Contact</nuxt-link></li>
            </ul>
        </nav>
        <h2>Produit</h2>
        <nav>
            <ul>
                <li>
                    <nuxt-link to="products/1">Produit 1</nuxt-link>
                </li>
                <li>
                    <nuxt-link to="products/2">Produit 2</nuxt-link>
                </li>
                <li>
                    <nuxt-link to="products/3">Produit 3</nuxt-link>
                </li>
            </ul>
        </nav>
    </main>
</template>