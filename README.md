#include<stdio.h>
#include<stdlib.h>
struct graph {

   int v;
   int e;
   int **adj;

};
struct graph *creategraph(){
        int i,j,e1,e2;
        struct graph *g;
        g=(struct graph *)malloc(sizeof(struct graph));
        printf("enter no of vertex");
        scanf("%d",&g->v);
        printf("enter no of edges");
        scanf("%d",&g->e);
        g->adj=malloc(sizeof(g->v * g->v));
        for(i=0;i<g->v;i++){
            for(j=0;j<g->v;j++){
                    g->adj[i][j]=0;
            }
        }
        for(i=0;i<g->e;i++){
            printf("enter edge e1 and e2");
            scanf("%d%d",&e1,&e2);
            g->adj[e1][e2]=1;
        }
        for(i=0;i<g->v;i++){
            for(j=0;j<g->v;j++){
                    printf("%d\n",g->adj[i][j]);
            }
            printf("\n");
        }
}
int main(){

   creategraph();
   return 0;
}
