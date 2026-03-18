public class CustomDataSetLoader extends FlatXmlDataSetLoader {
    @Override
    protected IDataSet createDataSet(Resource resource) throws Exception {
        IDataSet dataSet = super.createDataSet(resource);

        ReplacementDataSet replacement = new ReplacementDataSet(dataSet);
        replacement.addReplacementObject("[NULL]", null);

        return replacement;
    }
}
