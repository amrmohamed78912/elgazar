const products = [
    { id: 1, name: 'مسكن ألم', price: 15, quantity: 10, image: 'painkiller.jpg' },
    { id: 2, name: 'مضاد حيوي', price: 25, quantity: 5, image: 'antibiotic.jpg' },
    { id: 3, name: 'شراب سعال', price: 10, quantity: 20, image: 'cough-syrup.jpg' }
];

let cart = [];

function displayProducts() {
    const productList = document.getElementById('product-list');
    productList.innerHTML = '';

    products.forEach(product => {
        const productDiv = document.createElement('div');
        productDiv.classList.add('product');
        
        productDiv.innerHTML = `
            <img src="${product.image}" alt="${product.name}">
            <h3>${product.name}</h3>
            <p>السعر: ${product.price} ريال</p>
            <p>الكمية المتوفرة: ${product.quantity}</p>
            <button onclick="addToCart(${product.id})">إضافة إلى السلة</button>
        `;
        
        productList.appendChild(productDiv);
    });
}

function addToCart(productId) {
    const product = products.find(p => p.id === productId);
    if (product && product.quantity > 0) {
        const cartItem = cart.find(item => item.id === productId);
        if (cartItem) {
            cartItem.quantity++;
        } else {
            cart.push({ ...product, quantity: 1 });
        }
        product.quantity--;
        updateCart();
        displayProducts();
    }
}

function updateCart() {
    const cartItems = document.getElementById('cart-items');
    cartItems.innerHTML = '';
    let totalPrice = 0;

    cart.forEach(item => {
        cartItems.innerHTML += `<li>${item.name} - ${item.quantity} بسعر ${item.price * item.quantity} ريال</li>`;
        totalPrice += item.price * item.quantity;
    });

    document.getElementById('total-price').innerText = `إجمالي السعر: ${totalPrice} ريال`;
}

function checkout() {
    alert('تم إتمام عملية الشراء بنجاح!');
    cart = [];
    updateCart();
}

function showAdminLogin() {
    const password = prompt('من فضلك أدخل كلمة المرور:');
    if (password === '10017980') {
        document.getElementById('admin-section').style.display = 'block';
    } else {
        alert('كلمة المرور غير صحيحة.');
    }
}

function addNewProduct() {
    const name = document.getElementById('new-product-name').value;
    const image = document.getElementById('new-product-image').value;
    const price = parseFloat(document.getElementById('new-product-price').value);
    const quantity = parseInt(document.getElementById('new-product-quantity').value);

    if (name && image && price > 0 && quantity > 0) {
        const newProduct = {
            id: products.length + 1,
            name,
            price,
            quantity,
            image
        };
        products.push(newProduct);
        displayProducts();
        alert('تمت إضافة الدواء بنجاح!');
    } else {
        alert('يرجى تعبئة جميع الحقول بشكل صحيح.');
    }
}

displayProducts();
