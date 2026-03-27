# Travail Pratique 1 de Logan Bluteau

## Revues de code sur les components dans le sous-dossier `/src/`

### `/AppHeader/`

**Points positifs**

> J'aime bien le fait d'avoir fait une petite navigation entre la partie d'ajout de fruit et celle d'affichage des fruits.

```html
<nav class="app-header-actions">
  <button
    type="button"
    class="btn"
    :class="props.currentPage === 'add' ? 'btn-primary' : 'btn-outline-primary'"
    @click="emit('changePage', 'add')"
  >
    Ajouter
  </button>

  <button
    type="button"
    class="btn"
    :class="props.currentPage === 'list' ? 'btn-primary' : 'btn-outline-primary'"
    @click="emit('changePage', 'list')"
  >
    Liste
  </button>
</nav>
```

**Points négatifs**

> J'aurais aimé que le logo soit plus vers la gauche et que le titre du site soit à sa droite au lieu que tout soit empilé en étage.

```html
<header class="app-header">
  <img :src="logo" alt="Logo fruits" class="app-logo" />

  <div class="app-header-text">
    <h1 class="h2 fw-bold mb-2">Gestionnaire de fruits</h1>
    <p class="text-body-secondary mb-0">Créer des fruits</p>
  </div>
</header>
```



### `/FormFruit/`

**Points positifs**

>J'aime bien que le formulaire est été réutilisé pour ajouté,modifier et dupliquer. Le seul changement est le titre et la couleur. Je trouve que c'est
>une bonne idée
```ts 
<button class="btn btn-primary" type="submit" :disabled="submitted && !isValid">
    {{ fruitToEdit ? "Enregistrer" : duplicateDraft ? "Créer la copie" : "Ajouter" }}
</button>
```

```ts
<h2 class="h5 mb-3">
  {{ fruitToEdit ? "Modifier un fruit" : duplicateDraft ? "Dupliquer un fruit" : "Ajouter un fruit" }}  
</h2>
```

```ts 
function cancelDeleteFruit() {
  deleteMessage.value = "Suppression annulée.";
  fruitToDelete.value = null;
} 
```

### `/ListeFruit/`

**Points positif**

>J'aime le message qui affique qu'il n'y a pas de fruit pour le moment ainsi qu'il n'y a aucun résultat de la recherche.

```ts
<div v-if="fruits.length === 0" class="alert alert-info mb-0">
  {{ search.trim() ? "Aucun résultat." : "Aucun fruit pour le moment." }}
</div>
```

**Points négatif**

>Il faudrait garder la nomenclature des fichiers en anglais ou en français et non changer entre les deux.

## Revue de code pour le sous dossier /scripts/

### `/App/`

**Points positifs**

>J'aime bien l'ajout d'un message de confirmation de supression annulé.

```html
<div v-if="deleteMessage" class="alert alert-info">
    {{ deleteMessage }}
</div>
```
