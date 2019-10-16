<template>
    <div>
        <d-puzzle v-bind="puzzleConfig[level]" @next="handleNext" img="./puzzleimg/two.jpg"/>
    </div>
</template>
<script>
import DPuzzle from './Puzzle';
export default {
    components:{
        DPuzzle
    },
    data(){
        return{
            level:0,
            puzzleConfig:[
                { row:3,col:3,img:'./puzzleimg/three.jpg' },
                { row:4,col:4,img:'./puzzleimg/four.jpg' },
                { row:5,col:5,img:'./puzzleimg/five.jpg' },
                { row:6,col:6,img:'./puzzleimg/six.jpg' },
                { row:8,col:8,img:'./puzzleimg/two.jpg' },
            ]
        }
    },
    methods:{
        handleNext(){
            if(++ this.level == this.puzzleConfig.lenght){
                const answerFlag=window.confirm('已经是最后一关了，是否重新开始？');
                if(answerFlag){
                    this.level=0;
                }
            }
        }
    }
}
</script>