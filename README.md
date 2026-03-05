[app.js](https://github.com/user-attachments/files/25759161/app.js)
    /*const array = [1,2,3,4,'x']
    //console.log(array)
    //console.log(array[4]) //нумераця массива с 0
    console.log(array[array.length-2])//предпоследний элемент массива любой длины
    */
    const inpElement = document.getElementById('title')
    const btnCreate = document.getElementById('create')
    const listElement = document.getElementById('list')
    //const notes = ['1. Приготовить еду на ужин', '2. Сходить на тренировку']
    //console.log(inpElement.value)
        btnCreate.onclick = function (){
        if (inpElement.value.length === 0){
            return
        }
        const newNote = {
          title: inpElement.value,
          completed: false,
        }
        
    //     listElement.innerHTML +=`
    //     <li class="list-group-item d-flex justify-content-between align-items-center bg-white text-dark">
    //     <span>${inpElement.value}</span>
    //     <span>
    //       <span class="btn btn-success btn-sm">✓</span>
    //       <span class="btn btn-danger btn-sm">✕</span>
    //     </span>
    //   </li>
    //   `
    listElement.insertAdjacentHTML('beforeend', getNoteTemp(newNote))
    inpElement.value = ''
      //insertAdjacentHTML
    //listElement.insertAdjacentHTML('beforeend', )
    }
    function getNoteTemp(note) {
      console.log(note.completed)
    return `<li class="list-group-item d-flex justify-content-between align-items-center bg-white text-dark">
        <span class = "${note.completed ? 'text-decoration-line-through ' : ''}">${note.title}</span>
        <span>
          <span class="btn btn-success btn-sm">✓</span>
          <span class="btn btn-danger btn-sm">✕</span>
        </span>
      </li>`
    }
    // const person = {
    //     firstName: 'Oleg',
    //     lastName: 'Vasilenko',
    //     year: 2003,
    //     getFullName: function() {
    //     console.log(person.firstName)
    //     }
    //}
   // console.log(typeof notes)

    const notes = [{title: '1. Приготовить еду на ужин',
    completed: true,
    },
   { title: '2. Сходить на тренировку',
    completed: true,
    },
]  
function render () {
    listElement.innerHTML='' // Очищаем перед отрисовкой
    // for (let i = 0; i<notes.length; i++) {
    //     listElement.insertAdjacentHTML('beforeend', getNoteTemp(notes[i]))
    // }
    for (let note of notes) {
         listElement.insertAdjacentHTML('beforeend', getNoteTemp(note))
     }
    
}
render()

