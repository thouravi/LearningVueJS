# LearningVueJS
<!DOCTYPE html>
<html>
	<head>
    <title>VueJS</title>
    <meta charset="utf-8">
	<meta name="viewport" content="width=device-width, initial-scale=1">
	<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css">
	<link rel="stylesheet" href="style.css">
	<script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js"></script>
	</head>
	
	<body>
		
		<div id="root">
			<center>
				<div>
					<h1>Add New Book</h1>
					<form class="form-inline">
					<input type="text" class="form-control" v-model="newName" placeholder="Title"></input>
					<input type="text" class="form-control" v-model="newAuthor" placeholder="Author"></input>
					<input type="text" class="form-control" v-model="newDate" placeholder="Year"></input>
					<input type="text" class="form-control" v-model="newLanguage" placeholder="Language"></input>
					</br></br>
					<button @click="addNew" type="button" class="btn btn-default">Add Book</button>
					</form>
				</div>
				<hr class="style14">
				<div v-for="book in books">
					<div class="container">
					<div class="row">
					<div class="col-md-2">
					<h1> {{ book.name }} </h1> 
					<p> By <b>{{ book.author }}</b> </p>
					<p><b>{{ book.date }}</b> in <b>{{ book.language }}</b> </br></p>
					</div>
					</br></br></br>
					<div class="col-md-10">
					<form class="form-inline">
					<div class="form-group">
					<input type="text" class="form-control" v-model="book.name">
					</div>
					<div class="form-group">
					<input type="text" class="form-control" v-model="book.author">
					</div>
					<div class="form-group">
					<input type="text" class="form-control" v-model="book.date">
					</div>
					<div class="form-group">
					<input type="text" class="form-control" v-model="book.language">
					</div>
					</form>
					</div>
					</div>
					</div>
					<hr class="style14">
				</div></br></br>
				<p>Developed by Avi Thour - For Learning Purpose.</p>
			</center>
		</div>
	
	
    <script src="https://unpkg.com/vue@2.4.4/dist/vue.js"></script>

    <script>

      new Vue({
        el:'#root',
        data: {
		
        newName: '',
        newAuthor: '',
        newDate: '',
        newLanguage: '',
		  
		 books: [
            {
              name: 'Hamlet',
              author: 'William Shakespeare',
              date: '1609',
              language: 'English'
            },
            {
              name: 'A Boys Will',
              author: 'Robert Frost',
              date: '1913',
              language: 'English'
            }
          ]
        },
		
		methods: {
			addNew() {
				this.books.push({name: this.newName, author: this.newAuthor, date: this.newDate, language: this.newLanguage});
				this.newName = '';
				this.newAuthor = '';
				this.newDate = '';
				this.newLanguage = '';
			}
		}
      })
	  </script>
	</body>
</html>
