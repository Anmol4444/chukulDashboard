<template>
    <div class="form-signin" style="height: 200px;">

       
  <q-page
    class=" row justify-center items-center"
    style="background:#102B7B;"
  >
    


    <div class="column q-pa-lg">
      <div class="row">

     
        
          <div class="love" style="background-image: linear-gradient(#0040A0,#265CAF);width: 1000px;">

              <div class="b-up" style="left: 28%;position: relative;">
             <div class="q-pa-md q-m-md q-gutter-sm " >
    <q-btn-dropdown color="primary" icon="mail" label="Select Sectors" style="margin: 15px 5px;" />
    <q-btn-dropdown color="primary" icon="mail" label="Select Stocks
    " style="margin: 0px 25px;" />
    </div>
    </div>
   <hr>
  
            
          <div  class="b-down" style="margin: auto;left: 25%;position: relative;">
             <div class="q-pa-md q-m-md q-gutter-sm">
                <q-btn color="primary" icon="mail" label="Tabular" style="margin: 0px 5px;"/>
                <q-btn color="primary" icon="mail" label="Graph" style="margin: 0px 25px;"/>
                <q-btn color="primary" icon="mail"  label="Add/remove Dimension" style="margin: 0px 5px;"/>
                
               </div>
             </div>  
              
       
        

              
           <div class="q-pa-md">
    <q-table
  
      :rows="rows"
      :columns="columns"
      row-key="name"
      binary-state-sort
    >
      <template v-slot:body="props">
        <q-tr :props="props">
          <q-td key="name" :props="props">
            {{ props.row.name }}
            <q-popup-edit v-model="props.row.name">
              <q-input v-model="props.row.name" dense autofocus counter />
            </q-popup-edit>
          </q-td>
          <q-td key="calories" :props="props">
            {{ props.row.calories }}
            <q-popup-edit v-model="props.row.calories" title="Update calories" buttons>
              <q-input type="number" v-model="props.row.calories" dense autofocus />
            </q-popup-edit>
          </q-td>
          <q-td key="fat" :props="props">
            <div class="text-pre-wrap">{{ props.row.fat }}</div>
            <q-popup-edit v-model="props.row.fat">
              <q-input type="textarea" v-model="props.row.fat" dense autofocus />
            </q-popup-edit>
          </q-td>
          <q-td key="carbs" :props="props">
            {{ props.row.carbs }}
            <q-popup-edit v-model="props.row.carbs" title="Update carbs" buttons persistent>
              <q-input type="number" v-model="props.row.carbs" dense autofocus hint="Use buttons to close" />
            </q-popup-edit>
          </q-td>
          <q-td key="protein" :props="props">{{ props.row.protein }}</q-td>
          <q-td key="sodium" :props="props">{{ props.row.sodium }}</q-td>
          <q-td key="calcium" :props="props">{{ props.row.calcium }}</q-td>
          <q-td key="iron" :props="props"><div> <q-btn color="primary"  label="View Trend" style="margin: 0px 5px;"/></div></q-td>
        </q-tr>
      </template>
    </q-table>
    
      </div>
      <q-btn color="primary" icon="mail" label="Add Store" style="margin: 30px 25px;"/><br>
      
      
    
  </div>
  
     
        
      </div>
    </div>




       



  </q-page>


       
    </div>
</template>


<script>

import { ref } from 'vue';



const columns = [
  {
    name: 'name',
    required: true,
    align: 'left',
    field: row => row.name,
    format: val => `${val}`,
    sortable: true
  },
  { name: 'calories', align: 'center',  },
  { name: 'fat', label: 'Sector', field: 'fat', sortable: true },
  { name: 'carbs', label: 'EPS', field: 'carbs' },
  { name: 'protein', label: 'Network', field: 'protein' },
  { name: 'sodium', label: ' PEG', field: 'sodium' },
  { name: 'calcium', label: 'GRAM', field: 'calcium', sortable: true, sort: (a, b) => parseInt(a, 10) - parseInt(b, 10) },
  { name: 'iron', field: 'iron', sortable: true, sort: (a, b) => parseInt(a, 10) - parseInt(b, 10) }
]

const rows = [
  {
    name: 'Q1',
    calories: 78079,
     fat: 'Bank',
    carbs: 15,
    protein: 150,
    sodium: 0.98,
    calcium: 380,
    iron: '1%'
  },
  {
    name: 'Q2',
     calories: 78079,
     fat: 'Dev Ban',
    carbs: 15,
    protein: 150,
    sodium: 0.98,
    calcium: 380,
    iron: '1%'
  },
  {
    name: 'Q3',
    calories: 78079,
    fat: 'Hydro',
    
  },
  

]

export default {
  setup () {
    return {
      columns,
      rows: ref(rows)
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Laila&family=Oswald&family=Raleway&display=swap');

body{
  font-family: 'Laila', sans-serif;
}

.page{
  background-color: red;


}
.q-btn {
 border-radius: 20px;}
 .b-up .label{
   background-color: red;
 
}
.block{
  font-size: 12px;
}
.q-table
{
  background: linear-gradient(#529BDE,#254F9B);

}
.q-table__bottom{
  display: none;
}
.q-table tbody td
{
  color: white;
}
.text-right {
  color: white;
}
</style>