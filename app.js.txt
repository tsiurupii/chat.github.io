document.getElementById('productForm').addEventListener('submit', function(event) {
    event.preventDefault();

    // Получаем данные из формы
    const productName = document.getElementById('productName').value;
    const productPrice = document.getElementById('productPrice').value;
    const productImage = document.getElementById('productImage').value;

    // Создаем новый элемент для товара
    const product = document.createElement('div');
    product.className = 'product';
    product.innerHTML = `
        <h2>${productName}</h2>
        <p>Цена: ${productPrice} руб.</p>
        <img src="${productImage}" alt="${productName}">
        <button onclick="buyProduct('${productName}')">Купить</button>
    `;

    // Добавляем товар на страницу
    document.getElementById('products').appendChild(product);

    // Очищаем форму
    document.getElementById('productForm').reset();
});

function buyProduct(productName) {
    alert(`Вы купили ${productName}!`);
}
