# SimpleRecycleAdapter
简化创建 RecyclerView 的 Adapter 的工作



使用：

    public class TestAdapter extends SimpleRecycleAdapter<Student> {
    
        public TestAdapter(List<Student> data, Context context) {
            super(data, context);
        }
    
        @Override
        public void onBind(InnerViewHolder holder, int position) {
            super.onBind(holder, position);
            TextView textView = holder.getView(R.id.text);
            textView.setText("" + ((Student) getItem(position)).getName());
        }
    
        @Override
        public int getItemLayoutID() {
            return R.layout.test_item;
        }
    }
  
只需覆盖 onBind 和 getItemLayoutID 就好
