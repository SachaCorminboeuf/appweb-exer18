# Revue de code TP01 Sacha

## Revue de codes des components 

**MainScreen.vue** 

**Bon coup**
General
Les noms des fonctions est clair et précis.
Les fichiers sont bien séparer les un des autres 


J'ai bien aimer l'utulisation du Omit  pour la fonction ajouter. 
```ts
function handleAdd(newItemData: Omit<Item, "id">): void {
  const newItem: Item = {
    id: nextId++,
    ...newItemData,
  };
  items.value.push(newItem);
}
```

**EditItem**

Bon Coup

Bonne function pour valider le formulaire, simple et efficace. 

```ts
function isFormValid(): boolean {
  return (
    !!formData.name.trim() &&
    formData.price > 0 &&
    formData.stock >= 0 &&
    !!formData.description.trim()
  );
}
```

**Mauvais coup**
On repete plusieurs fois la fonction isFormValid
