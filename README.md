# EnumExampe

public enum EnumExample {

    ENUMID( "1");

    private String id;

    private static final Map<String, EnumExample> TYPE_MAP = Stream.of(EnumExample.values())
            .collect(Collectors.toMap(EnumExample::getId, Function.identity()));

    public static GameType fromValue(final String type) {
        if (TYPE_MAP.containsKey(type)) {
            return TYPE_MAP.get(type);
        }
        throw new IllegalArgumentException ("Unknown channel type for value : " + type);
    }
}
